---
SMQM: UNASSIGNED
Author: Clinton Wolfe <clinton@omniti.com>
Status: Draft
License: Apache 2.0
---

# Cookbook documents its attributes

The cookbook documents the attributes that it defines or uses.

Attributes definitions will be sought in the attributes/*.rb files, if any.

Attribute usage will be sought in the recipes and templates.

For each attribute referenced, there must be a mention in the README.

Cookbook consumers should have a clear reference for the attributes that the cookbook expects.

### Verification

Pseudocode:

    readme = read_readme(cookbook)
    it 'documents its attributes' do
      find_all_attributes(cookbook).each do |attribute_name|
        expect(readme).to contain attribute_name
      end
    end
