---
SMQM: UNASSIGNED
Author: Nathen Harvey <nharvey@chef.io>
Status: Draft
License: Apache 2.0
---

# Cookbook lists maintainer's email address

The cookbook has a `maintainer_email` specified as part of its metadata.

Cookbook consumers should know whom to contact with questions, issues, or praise for a cookbook.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has a maintainer_email' do
      expect(cookbook.maintainer_email).to_not be_nil
    end

### Points

* Positive Points:  1
* Negative Points: 20

One point will be awarded if the quality metric is met.

Ten points will be deducted if the quality metric is not met.
