# Stedi's default Renovate Bot configurations

Note: before you adopt this default configuration in your repo, it's highly recommended that you have branch protection and requisite testing in place – these configurations default to auto-merging dependency update PRs.

## Useful tidbits
* Package rules are applied in the array order they're defined in.  
  Each rule is applied if it matches.  
  [(source)](https://github.com/renovatebot/config-help/issues/497#issuecomment-574612328)
* What does the regex `!/^[~^]?0/` mean?
  * We use this regex to enable automerge for patch and minor upgrades.
  * This regex looks for versions that have a 0 major version (e.g. `0.50.4` or `~0.0.1`) .
  * This can be a pinned version (no prefix), a version that allows for upgrading patch (~), or one that allow for patch and minor versions (^).
  * With the `!` at the beginning it finally says "only allow versions that don't follow this pattern".
