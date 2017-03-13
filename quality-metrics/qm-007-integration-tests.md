---
SMQM: 007
Author: JJ Asghar <jj@chefio>
Status: Accepted
License: Apache 2.0
---

# Cookbook includes integration tests

There should be at least one of the following directories with test files:

* serverspec
* bats
* TBD

Integration testing allows you to assert the state of the converged node to ensure it is in the desired state.

Integration testing is pinnacle to velocity and verifying community cookbooks do what we expect.

### Verification

Pseudocode or actual code that can be used to automatically verify the rule and/or assign appropriate points.

```bash
   [ $(find test/integration/ -name '*_spec.rb' | wc -l) -ge $(find recipes/ -name '*.rb' | wc -l ) ]
```
