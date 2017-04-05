---
SMQM: 014
Author: Robb Kidd <robb@thekidds.org>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Cookbook source has a tag matching cookbook version

The source repository for a cookbook version has a tag matching the version of
the cookbook declared in metadata.

* Depends on QM-005, metadata contains a `source_url`
* Initially limited to cookbook projects whose source is available in GitHub.

To facilitate troubleshooting, consumers of a cookbook should be able to trace
the version they are using to the state of the cookbook's source at the time the
cookbook build artifact was produced.

### Verification

Pseudocode:

    it 'has a tag in source that matches the cookbook version' do
      cookbook_version = cookbook_version_from_metadata
      source_repo_response = http_get "#{source_url}/tree/#{cookbook_version}"
      expect(source_repo_response).to be 200
    end

... or ...

    it 'has a tag in source that matches the cookbook version' do
      # require 'octokit'
      source_tags = octokit_tags_for_repo cookbook_source_url_from_metadata
      expect(source_tags).to include cookbook_version_from_metadata
    end
