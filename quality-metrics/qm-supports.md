---
SMQM: UNASSIGNED
Author: John Bellone <jbellone@bloomberg.net>
Status: Draft
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

### Points

* Positive Points: 1
* Negative Points: 10

One point will be awarded if the quality metric is met.

Ten points will be deducted if the quality metric is not met.
