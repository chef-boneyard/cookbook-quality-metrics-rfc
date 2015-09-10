
* It converges without error.

    ```
    it 'converges successfully' do
      expect { chef_run }.to_not raise_error
    end
    ```

* It converges without error using Fauxhai data for each supported platform.
* It is updated and released on a regular basis
  * time since last release
  * time since last change in source code repository
  * number of commits not released
* It includes a README.md with more than the boilerplate copy.
* It includes a MAINTAINERS.md with contact information for each authorized MAINTAINER and Supermarket Collaborator.
  * There is more than one maintainer.
  * What is the optimal range?  5-7 maintainers?
  * We should not call it the 'bus factor'
* It includes a .kitchen.yml which includes a platform declaration for each of the platforms listed as a `supports` in the cookbook's metadata.
* `kitchen test` completes successfully.
* It includes rspec-based unit tests that pass.
* The README includes a badge indicating status of Code Climate and TravisCI tests.
  * Code Climate for Foodcritic and Rubocop
  * TravisCI for ChefSpec
* It includes a `Berksfile` that lists all dependencies.
* It includes a CHANGELOG.md that is updated with each release.
