---
SMQM: 007
Author: Nathen Harvey <nharvey@chef.io>
Status: Accepted
License: Apache 2.0
---

# Cookbook has a version other than `0.0.0`

The cookbook sets a version other than `0.0.0` in its metadata.

Cookbooks without a version specified in their metadata will default to `0.0.0`.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has a version' do
      expect(cookbook.version).to_not eq("0.0.0")
    end
