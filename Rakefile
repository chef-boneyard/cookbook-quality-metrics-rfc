#
# Copyright:: 2015-2019, Chef Software, Inc.
# License:: Apache License, Version 2.0
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

require 'rake'

SOURCE = File.join(File.dirname(__FILE__), 'MAINTAINERS.toml')
TARGET = File.join(File.dirname(__FILE__), 'MAINTAINERS.md')

# The list of repositories that teams should own
REPOSITORIES = ['chef-cookbooks/cookbook-quality-metrics'].freeze

begin
  require 'tomlrb'
  require 'octokit'
  require 'pp'
  task default: 'maintainers:generate'

  namespace :maintainers do
    desc 'Generate MarkDown version of MAINTAINERS file'
    task :generate do
      maintainers = Tomlrb.load_file SOURCE
      out = "<!-- This is a generated file. Please do not edit directly -->\n\n"
      out << "<!-- Modify MAINTAINERS.toml and run `rake maintainers:generate` to regenerate. -->\n\n"
      out << '# ' + maintainers['Preamble']['title'] + "\n\n"
      out << maintainers['Preamble']['text'] + "\n"
      out << components(maintainers['people'], maintainers['Org']['Components'])
      File.open(TARGET, 'w') do |fn|
        fn.write out
      end
    end

    desc 'Synchronize GitHub teams'
    task :synchronize do
      Octokit.auto_paginate = true
      get_github_teams
      prepare_teams(source['Org']['Components'].dup)
      sync_teams!
    end
  end

  def github
    @github ||= Octokit::Client.new(netrc: true)
  end

  def source
    @source ||= Tomlrb.load_file SOURCE
  end

  def teams
    @teams ||= { 'quality-metrics-maintainers' => { 'title' => 'Cookbook Quality Metrics' } }
  end

  def add_members(team, name)
    teams['quality-metrics-maintainers']['members'] ||= []
    teams['quality-metrics-maintainers']['members'] << name
    teams[team] ||= {}
    teams[team]['members'] ||= []
    teams[team]['members'] << name
  end

  def set_team_title(team, title)
    teams[team] ||= {}
    teams[team]['title'] = title
  end

  def gh_teams
    @gh_teams ||= {}
  end

  # we have to resolve team names to ids. While we're at it, we can get the privacy
  # setting, so we know whether we need to update it
  def get_github_teams
    github.org_teams('chef-cookbooks').each do |team|
      gh_teams[team[:slug]] = { 'id' => team[:id], 'privacy' => team[:privacy] }
    end
  end

  def get_github_team(team)
    github.team_members(gh_teams[team]['id']).map do |member|
      member[:login]
    end.sort.uniq.map(&:downcase)
  rescue
    []
  end

  def create_team(team)
    puts "creating new github team: #{team} with title: #{teams[team]['title']} "
    t = github.create_team('chef-cookbooks', name: team, description: teams[team]['title'],
                                             privacy: 'closed', repo_names: REPOSITORIES,
                                             accept: 'application/vnd.github.ironman-preview+json')
    gh_teams[team] = { 'id' => t[:id], 'privacy' => t[:privacy] }
  end

  def compare_teams(current, desired)
    # additions are the subtraction of the current state from the desired state
    # deletions are the subtraction of the desired state from the current state
    [desired - current, current - desired]
  end

  def prepare_teams(cmp)
    %w(text paths).each { |k| cmp.delete(k) }
    if cmp.key?('team')
      team = cmp.delete('team')
      add_members(team, cmp.delete('lieutenant')) if cmp.key?('lieutenant')
      add_members(team, cmp.delete('maintainers')) if cmp.key?('maintainers')
      set_team_title(team, cmp.delete('title'))
    else
      %w(maintainers lieutenant title).each { |k| cmp.delete(k) }
    end
    cmp.each { |_k, v| prepare_teams(v) }
  end

  def update_team(team, additions, deletions)
    create_team(team) unless gh_teams.key?(team)
    update_team_privacy(team)
    add_team_members(team, additions)
    remove_team_members(team, deletions)
  rescue
    puts "failed for #{team}"
  end

  def update_team_privacy(team)
    return
    return if gh_teams[team]['privacy'] == 'closed'
    puts "Setting #{team} privacy to closed from #{gh_teams[team]['privacy']}"
    github.update_team(gh_teams[team]['id'], privacy: 'closed',
                                             accept: 'application/vnd.github.ironman-preview+json')
  end

  def add_team_members(team, additions)
    additions.each do |member|
      puts "Adding #{member} to #{team}"
      github.add_team_membership(gh_teams[team]['id'], member, role: 'member',
                                                               accept: 'application/vnd.github.ironman-preview+json')
    end
  end

  def remove_team_members(team, deletions)
    deletions.each do |member|
      puts "Removing #{member} from #{team}"
      github.remove_team_membership(gh_teams[team]['id'], member,
                                    accept: 'application/vnd.github.ironman-preview+json')
    end
  end

  def sync_teams!
    teams.each do |name, details|
      current = get_github_team(name)
      desired = details['members'].flatten.sort.uniq.map(&:downcase)
      additions, deletions = compare_teams(current, desired)
      update_team(name, additions, deletions)
    end
  end

  def get_person(person)
    source['people'][person]
  end

  def components(list, cmp)
    out = '## ' + cmp.delete('title') + "\n\n"
    out << cmp.delete('text') + "\n" if cmp.key?('text')
    out << "To mention the team, use @chef-cookbooks/#{cmp.delete('team')}\n\n" if cmp.key?('team')
    if cmp.key?('lieutenant')
      out << "### Lieutenant\n\n"
      out << person(list, cmp.delete('lieutenant')) + "\n\n"
    end
    out << maintainers(list, cmp.delete('maintainers')) + "\n" if cmp.key?('maintainers')
    cmp.delete('paths')
    cmp.each { |_k, v| out << components(list, v) }
    out
  end

  def maintainers(list, people)
    o = "### Maintainers\n\n"
    people.each do |p|
      o << person(list, p) + "\n"
    end
    o
  end

  def person(list, person)
    out = if list[person].key?('GitHub')
            "* [#{list[person]['Name']}](https://github.com/#{list[person]['GitHub']})"
          else
            "* #{list[person]['Name']}"
          end
    out << "\n  * Slack - #{list[person]['Slack']}" if list[person].key?('Slack')
    out << "\n  * [@#{list[person]['Twitter']}](https://twitter.com/#{list[person]['Twitter']})" if list[person].key?('Twitter')
    out << "\n  * [#{list[person]['email']}](mailto:#{list[person]['email']})" if list[person].key?('email')
    out << "\n  * #{list[person]['phone']}" if list[person].key?('phone')
    out << "\n  * [ServerFault](#{list[person]['ServerFault']})" if list[person].key?('ServerFault')
    out
  end
rescue LoadError
  STDERR.puts "\n*** Gems missing. Please run bundle install.\n\n"
end
