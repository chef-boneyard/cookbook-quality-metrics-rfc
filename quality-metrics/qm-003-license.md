---
SMQM: 003
Author: Nathen Harvey <nharvey@chef.io>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Cookbook has an open source license

Cookbook is licensed using an open source license.

Acceptable licenses are:

* Apache-2.0, Apache 2.0, apachev2
* MIT, mit
* GPL-2.0, GNU Public License 2.0, gplv2
* GPL-3.0, GNU Public License 3.0, gplv3

Licenses listed using the [SPDX License Identifiers](https://spdx.org/licenses/) are preferred.

Cookbooks without open source licenses may not be modifiable and may not even be legally used by consumers.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has an open source license' do
      expect(cookbook_version.license).to match(/Apache-2.0|Apache 2.0|apachev2|MIT|mit|GPL-2.0|GNU Public License 2.0|gplv2|GPL-3.0|GNU Public License 3.0|gplv3/i)
    end
