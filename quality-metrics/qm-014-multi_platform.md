---
SMQM: 14
Author: Tim Smith <tsmith@chef.io>
Status: Draft
License: Apache 2.0
---

# Supports Multiple Platforms

The cookbook author has indicated support for multiple platforms by including more than 1 supports attribute in the metadata.rb

Well written cookbooks include support for a diverse set of platforms. It's key that those platforms are noted in the metadata.rb so that they will be listed on Supermarket.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule.

    it 'supports multiple platforms' do
      expect(metadata.rb).to contain >1 'supports'
    end
