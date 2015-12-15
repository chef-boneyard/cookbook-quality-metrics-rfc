---
SMQM: 10
Author: John Bellone <jbellone@bloomberg.net>
Status: Accepted
License: Apache 2.0
---

# Cookbook lists at least one platform it supports

The cookbook has a list of the platforms that it `supports` specified as
part of its metadata.

Cookbook consumers should have confidence in knowing that a cookbook
is intended to work on a platform in the supports list.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```ruby
it 'has a supports' do
  expect(cookbook.supports).to_not be_nil
end
```
