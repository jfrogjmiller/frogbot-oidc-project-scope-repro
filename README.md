# frogbot-oidc-project-scope-repro

Throwaway public repo for a follow-up on JFrog support case 412003.

Question under test: when a customer authenticates frogbot via OIDC and
their JFrog OIDC identity mapping is project-scoped, but frogbot itself is
never configured with a matching `JF_GIT_PROJECT`/`JF_PROJECT` (they don't
use JFrog Projects), do JAS/watches/entitlement lookups start failing with
403s that don't occur with a plain access token or with a global (non
project-scoped) identity mapping? Is this different between frogbot v2 and
v3?

See `.github/workflows/` for the test matrix. `JF_GIT_PROJECT` is
intentionally left unset in every scenario.

Re-triggering a fresh, isolated scan session (case 412003 follow-up).
Trigger official-action test run.
