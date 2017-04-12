---
SMQM: UNASSIGNED
Author: Peter Burkholder <pburkholder@pobox.com>
Status: Draft
License: Apache 2.0
---

# Cookbook does not require external network dependencies

The cookbooks should support sites with no external network access. If the test-kitchen `default` test suite passes by accessing external dependencies, such as gems, packages or tarballs, then test-kitchen should also pass a suite that has no external dependencies, perhaps by using local paths to artifacts, and a suite that uses local (non-Internet) repositories.

### Verification

Pseudocode:

    when all_network_connections_are_dropped do
      expect(test_suite_with_paths_to_artifacts).to pass
    end

    when all_network_connections_are_dropped do
      when connections_to_internal_networks_are_allowed do
        expect(test_suite_with_internal_repositories).to pass
      end
    end
