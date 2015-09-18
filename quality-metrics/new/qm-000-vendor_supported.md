---
SMQM: UNASSIGNED
Author: Matt Ray <matt@chef.io>
Status: Draft
License: Apache 2.0
---

# The cookbook is supported by the vendor

The vendor of the product or project managed by the cookbook acknowledges and
accepts support responsibilities for the cookbook.

* The vendor is listed as a contact email address for the cookbook in the README
* Chef's Partner Engineering is listed as a contact email address for the cookbook in the README
* Supermarket represents the cookbook as "Vendor Supported" in some form (badge?)

If a vendor chooses to support a cookbook for their product, this is an
indicator to users that there is an expectation of quality and support. This
designation is not automated and will require interaction with Chef's Partner
Engineering team (partnereng@chef.io) and potential partners are encouraged to
reach out to for assistance getting high-quality cookbooks published and
publicized. This does not preclude alternate implementations or other scoring
metrics.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has partnereng@chef.io as a maintainer' do
      expect(cookbook.maintainer).to match(/partnereng@chef.io/i)
    end

### Points

* Positive Points: 1
* Negative Points: 0

There is no penalty for not being a partner-supported cookbook and this may be
most appropriately presented as metadata for the cookbook to be used for sorting
instead of scoring.
