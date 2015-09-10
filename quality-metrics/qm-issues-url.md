---
SMQM: Unassigned
Author: John Bellone <jbellone@bloomberg.net>
Status: Draft
License: Apache 2.0
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

### Points
- Positive Points: 1
- Negative Points: 20

One point will be awarded if the quality metric is met.

Twenty points will be deducted if the quality metric is not met.
