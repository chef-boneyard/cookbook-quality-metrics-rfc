---
SMQM: Unassigned
Author: John Bellone <jbellone@bloomberg.net>
Status: Draft
License: Apache 2.0
---

# Cookbook lists a source address for repository

The cookbook has a `source_url` specified as part of its metadata.

Cookbook consumers should know where to look for the source code to
take a look at previous releases, pull-requests or unreleased changes.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```ruby
it 'has a issues_url' do
  expect(cookbook.source_url).to_not be_nil
end
```

### Points
- Positive Points: 1
- Negative Points: 50

One point will be awarded if the quality metric is met.

Fifty points will be deducted if the quality metric is not met.
