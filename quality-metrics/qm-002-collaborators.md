---
SMQM: 002
Author: Nathen Harvey <nharvey@chef.io>
Status: Accepted
License: Apache 2.0
---

# Cookbook has collaborators on the Supermarket

The cookbook has one or more collaborators listed on the Supermarket.

Having a collaborator means that there is more than one person with permission to release new versions of the cookbook.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    passes? = cookbook.collaborators.count >= 1

