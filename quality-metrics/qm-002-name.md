---
SMQM: 002
Author: Nathen Harvey <nharvey@chef.io>
Status: Accepted
License: Apache 2.0
---

# Cookbook has a Name

The cookbook has a `name` specified as part of its metadata.

Modern versions of the Chef Server require each cookbook has a `name` attribute.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has a name' do
      expect(cookbook.name).to_not be_nil
    end
