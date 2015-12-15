---
SMQM: 15
Author: Tim Smith <tsmith@chef.io>
Status: Accepted
License: Apache 2.0
---

# Includes CONTRIBUTING.MD file

The cookbook includes a `CONTRIBUTING.md` file in the root of the cookbook directory with instructions for contributing to the cookbook.

Proper contributing documentation is an important aide to ease the barrier to cookbook contribution and therefore should be included in all published cookbooks.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule.

    it 'has a contributing doc' do
      expect(CONTRIBUTING.md).to exist
    end
