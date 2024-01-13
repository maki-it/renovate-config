# Renovate config for Maki IT

This directory contains all default configutions for the Renovate bot.

See also [Renovate Docs - Shareable Config Presets](https://github.com/renovatebot/renovate/blob/main/docs/usage/config-presets.md).

## Preset usage in repos

Whenever repository onboarding happens, Renovate checks for a a default config to extend.
Renovate will check for a repository called `renovate-config` with a `default.json` file in the parent user/group/org of the repository.
On platforms that support nested groups (e.g. GitLab), Renovate will check for this repository at each level of grouping, from nearest to furthest, and use the first one it finds.
On all platforms, it will then look for a repository named like `.{{platform}}` (e.g. `.github`) with a `renovate-config.json`, under the same top-level user/group/org.

If found, that repository's preset will be suggested as the sole extended preset, and any existing `onboardingConfig` config will be ignored/overridden.
For example the result may be:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["local>myorgname/.github:renovate-config"]
}
```

### default.json

```json
{
  "extends": ["github>maki-it/.github/renovate"]
}
```

### python.json

```json
{
  "extends": ["github>maki-it/.github/renovate:python"]
}
```

From then on Renovate will use the Renovate config from the preset repo's default branch. You do not need to add it as a devDependency or add any other files to the preset repo.
