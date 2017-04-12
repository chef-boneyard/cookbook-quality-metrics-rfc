---
SMQM: 001
Author: Nathen Harvey <nharvey@chef.io>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Published to the Supermarket

* The cookbook is published to the Supermarket
* The cookbook is not deprecated
* The cookbook is not up for adoption

Deprecated or adoptable cookbooks should be used with extreme caution.

### Verification

This is pseudocode

    it 'is published to the supermarket' do
      expect((cookbook.deprecated? && cookbook.up_for_adoption?)).to be false
    end
