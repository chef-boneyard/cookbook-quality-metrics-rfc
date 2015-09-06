---
SMQM: UNASSIGNED
Author: Nathen Harvey <nharvey@chef.io>
Status: Draft
License: Apache 2.0
---

# Cookbook has a version other than `0.0.0`

The cookbook sets a version other than `0.0.0` in its metadata.

Cookbooks without a version specified in their metadata will default to `0.0.0`.  

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has a version' do
      expect(cookbook.version).to_not eq("0.0.0")
    end

### Points

* Positive Points:  1
* Negative Points: 10

One points will be awarded if the quality metric is met.

Ten points will be deducted if the quality metric is not met.
