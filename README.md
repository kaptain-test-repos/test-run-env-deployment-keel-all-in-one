# Test Run Env Deployment Keel All In One

E2E test repo for the `kubernetes-run-environment` build in buildon-github-actions.

Tests deployMode `deployment` with imageAutoUpdateProvider `keel`, the
all-in-one cluster-scope model (`clusterScopedDelegation: self`, cluster-admin
role, env applies its own cluster-scoped resources), the fully GENERATED
ConfigMap/Secret path (create-if-not-provided, no supplied templates), and the
single-namespace rule with checksum-named resources.

Pending notes:

- Uses draft schema fields (`clusterScopedDelegation`) from the uncommitted
  `spec-kaptainpm-schema` repo; the schema must be faked into the build before
  this repo can build.
- The referenced reusable workflow does not exist yet; hook scripts carry only
  the generic env-var assertions until the reference scripts land, then
  behaviour assertions (manifest shapes, checksum names, keel annotations)
  get added.
