---
SMQM: 003
Author: Nathen Harvey <nharvey@chef.io>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Cookbook has an open source license

Cookbook is licensed using an open source license.

Acceptable licenses are any OSI-approved open source license. The [Software
Package Data Exchange® (SPDX®) specification](https://spdx.org/licenses/) will
be used to identify licenses and their approval status with the OSI.

Cookbooks without open source licenses may not be modifiable and may not even be legally used by consumers.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has an open source license' do
      expect(collection_of_osi_approved_license_strings)
        .to include(cookbook_version.license)
    end
