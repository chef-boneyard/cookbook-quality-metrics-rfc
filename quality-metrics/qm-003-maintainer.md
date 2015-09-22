---
SMQM: 003
Author: Nathen Harvey <nharvey@chef.io>
Status: Accepted
License: Apache 2.0
---

# Cookbook lists a maintainer

The cookbook lists a `maintainer` as part of its metadata.

Cookbook consumers should know whom to contact with questions, issues, or praise for a cookbook.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has a maintainer' do
      expect(cookbook.maintainer).to_not be_nil
    end
