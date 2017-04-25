---
SMQM: UNASSIGNED
Author: Clinton Wolfe <clinton@omniti.com>
Status: Draft
License: Apache 2.0
---

# Cookbook declares user interface(s)

The cookbook explicitly declares a list of user interface mechanisms
in its metadata.  Value is to be a list of zero or more of the values:

* 'attributes' - the cookbook is configured using attributes
* 'databags' - usage of the cookbook `requires` databags
* 'resources' - the cookbook defines resources to be referenced in the user's recipes
* 'dsl' - the cookbook extends or alters the behavior of one or more Chef DSLs.

Cookbook consumers should be able to easily determine how they are to interact
with the cookbook.  Supermarket searches should be able to filter based on interface
(e.g. no cookbooks that require data bags).

### Verification

Pseudocode:

    it 'declares its user_interfaces' do
      expect(cookbook.user_interfaces).to_not be nil
    end
