---
SMQM: 013
Author: Tim Smith <tsmith@chef.io>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Cookbook Includes TESTING.MD File

The cookbook includes a `TESTING.md` file in the root of the cookbook directory with instructions for testing the cookbook.

Proper testing documentation is an important aide to ease the barrier to cookbook contribution and improve cookbook quality. Therefor a testing document should be included in all published cookbooks.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule.

    it 'has a testing doc' do
      expect(TESTING.md).to exist
    end
