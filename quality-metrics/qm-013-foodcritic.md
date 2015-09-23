---
SMQM: 013
Author: Nathen Harvey <nharvey@chef.io>
Status: Accepted
License: Apache 2.0
---

# Cookbook Passes Foodcritic

The cookbook should pass Foodcritic correctness and metadata testing.

Code that follows common standards is easier to read, write, and maintain.

### Verification

This is pseudocode:

    `foodcritic . --tags correctness,metadata`
