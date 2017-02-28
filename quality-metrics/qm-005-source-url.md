---
SMQM: 005
Author: John Bellone <jbellone@bloomberg.net>
Status: Closed
License: Apache 2.0
---

# Cookbook lists a source address for repository

The cookbook has a `source_url` specified as part of its metadata.

Cookbook consumers should know where to look for the source code to
take a look at previous releases, pull-requests or unreleased changes.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```ruby
it 'has a source_url' do
  expect(cookbook.source_url).to_not be_nil
end
```

# Status

This quality metric has been closed and is currently implemented as part of the [Cookbook Passes Foodcritic](qm-009-foodcritic.md).  [FC0065 - Ensure source_url is set in metadata](http://www.foodcritic.io/#FC065).
