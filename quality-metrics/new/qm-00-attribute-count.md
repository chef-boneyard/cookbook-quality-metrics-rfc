---
SMQM: UNASSIGNED
Author: David Aronsohn <WagThatTail@Me.com>
Status: Draft
License: Apache-2.0
---

# Score penalty on Attribute cound

A score modifier based on the count of attributes in files.

* Greater than 20 attributes should be a penalty
* Greater than 50 should be another pentalty
* Greater than 100 should be another pentalty

A quality community cookbook should have as few attributes as possible by default for tuning.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

    it 'has less than 21 attributes' do
      expect(attributes declared in atributes/*.rb).to be lt 21
    end
    it 'has less than 51 attributes' do
      expect(attributes declared in atributes/*.rb).to be lt 51
    end
    it 'has less than 100 attributes' do
      expect(attributes declared in atributes/*.rb).to be lt 100
    end
