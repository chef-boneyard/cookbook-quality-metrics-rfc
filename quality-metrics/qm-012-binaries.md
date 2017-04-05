---
SMQM: 012
Author: Clinton Wolfe <clintons@omniti.com>
Status: In Progress - Admin Only
License: Apache-2.0
---

# Cookbook does not contain binaries

The cookbook should not contain any binary files.

Cookbook consumers should be able to examine the contents of the
cookbook's source code in order to evaluate its actions and security
implications.

Community cookbooks that need to install binaries should obtain them
from signed artifact repositories.

### Verification

Pseudocode:

    it 'does not contain binaries' do
      list_all_files(cookbook).each do |file|
         expect(file).to_not be binary
      end
    end
