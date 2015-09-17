---
SMQM: UNASSIGNED
Author: JJ Asghar <jj@chefio>
Status: Draft
License: Apache 2.0
---

# Integration Testing

There should be at least one of the following with integration testing:
* serverspec
* bats
* TBD

With integration testing you can verify via test-kitchen that the cookbook does what you expect it to do, without checking it by hand.

Integration testing is pinnacle to velocity and verifying community cookbooks are what we expect them to be.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```bash
   [ $(find test/integration/default/ -name '*_spec.rb' | wc -l) -ge $(find recipes/ -name '*.rb' | wc -l ) ]
```

### Points

* Positive Points: TBD
* Negative Points: TBD

TBD points will be awarded if the quality metric is met.

TBD points will be deducted if the quality metric is not met.
