---
SMQM: 004
Author: John Bellone <jbellone@bloomberg.net>
Status: Closed
License: Apache-2.0
---

# Cookbook lists address for issues

The cookbook has a `issues_url` specified as part of its metadata.

Cookbook consumers should know where to create issues - including
bugs, feature requests, etc - from the Supermarket page.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```ruby
it 'has a issues_url' do
  expect(cookbook.issues_url).to_not be_nil
end
```

# Status

This quality metric has been closed and is currently implemented as part of the [Cookbook Passes Foodcritic](qm-009-foodcritic.md).  [FC0064 - Ensure issues_url is set in metadata](http://www.foodcritic.io/#FC064).
