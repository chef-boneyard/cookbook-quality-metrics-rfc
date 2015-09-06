---
SMQM: UNASSIGNED
Author: Nathen Harvey <nharvey@chef.io>
Status: Draft
License: Apache 2.0
---

# Cookbook has an open source license

Cookbook is licensed using an open source license.

Acceptable licenses are:

* Apache 2.0
* GNU Public License 2.0
* GNU Public License 3.0
* MIT

Cookbooks without open source licenses may not be modifiable and may not even be legally used by consumers.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has an open source license' do
      expect(cookbook_version.license).to match(/Apache 2.0|apache2|GNU Public License 2.0|gplv2|GNU Public License 3.0|gplv3|MIT/i)
    end

### Points

* Positive Points:  1
* Negative Points: 100

One point will be awarded if the quality metric is met.

One hundred points will be deducted if the quality metric is not met.
