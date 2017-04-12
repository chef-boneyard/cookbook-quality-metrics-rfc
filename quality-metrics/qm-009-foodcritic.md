---
SMQM: 009
Author: Nathen Harvey <nharvey@chef.io>
Status: Implemented
License: Apache-2.0
---

# Cookbook Passes Foodcritic

The cookbook should pass Foodcritic correctness and metadata testing.

Code that follows common standards is easier to read, write, and maintain.

Implemented in [Supermarket 2.8.0 (2016-07-05)](https://github.com/chef/supermarket/blob/master/CHANGELOG.md#280-2016-07-05)

This is pseudocode:

    `foodcritic . --tags correctness,metadata`
