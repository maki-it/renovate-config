# Renovate Config Presets

A collection of custom Renovate config presets to be used by Maki IT repos.

Updates made to these configs will automatically and immediately be made available to all repos that are referencing them. No changes in the individual repos is required as long as they have the reference set up in the extends property.

## Usage

To make use of these preset you need to add them to your `extends` array within your repos `renovate.json`.

Multiple presets can be specified and they build on top of each other.

(For full details please refer to the [Renovate docs](https://docs.renovatebot.com/config-presets/#how-to-use-preset-configs)).

The presets found in this repo make use of [JSON5](https://json5.org/) so that comments can be added to make them more maintainable.

### Minimal/Default example

```json
{
  "extends": [
    "github>maki-it/renovate-config:default.json5"
  ],
}
```

### Language specific example

```json
{
  "extends": [
    "github>maki-it/renovate-config:default.json5",
    "github>maki-it/renovate-config:lang-python.json5"
  ],
}
```

## Resources

* [Shareable config preset](https://docs.renovatebot.com/config-presets/)
* [Key concepts - Presets](https://docs.renovatebot.com/key-concepts/presets/)
* [Credential encryption](https://app.renovatebot.com/encrypt)
