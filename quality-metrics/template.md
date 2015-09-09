---
SMQM: UNASSIGNED
Author: JJ Asghar <jj@chefio>
Status: Draft, Accepted, Implemented, Closed
License: Apache 2.0
---

# Integration Testing

There should be at least one of the following with integration testing:
* serverspec
* bats
* TBD

With integration testing you can verify via test-kitchen that the cookbook does what you expect it to do, without checking it by hand.

Integration testing is pinical to velocity and verifing community cookbooks are what we expect them to be.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

  find test/integration/default/ --name _spec.rb > 3

### Points

* Positive Points:  50
* Negative Points: 10

Positive points will be awarded if the quality metric is met.

Negative points will be deducted if the quality metric is not met.
