# Gherkin lint

An unofficial [fork](https://github.com/ohlori/gherkin-lint) of [gherkin-lint](https://github.com/gherkin-lint/gherkin-lint), published as [`@ohlori/gherkin-lint`](https://www.npmjs.com/package/@ohlori/gherkin-lint). Based on upstream `4.2.4`. 

Current fork version: **4.3.2**. It is not affiliated with or endorsed by the original authors.

## Changes

- Supports modern Gherkin `Rule` blocks, including Rule-scoped `Background`s.
- Scopes `no-dupe-scenario-names` by `Rule`: the same scenario name under different Rules is allowed; duplicates under the same Rule (or both at Feature level) are still flagged.
- Allows indentation-only blank lines inside DocStrings (`no-trailing-spaces`).
- Runs the stylish formatter from source and refreshes production dependencies.

### `no-dupe-scenario-names` + Rules example

```gherkin
Rule: Users Tab
  Scenario: [Pagination] Next page
    Then users on the next page are shown

Rule: Companies Tab
  Scenario: [Pagination] Next page
    Then companies on the next page are shown
```

Those two scenarios share a name but live under different Rules, so the rule does not report a duplicate.

Configure per-feature duplicate checks like this:

```json
{
  "no-dupe-scenario-names": ["on", "in-feature"]
}
```

## Install

```sh
npm install @ohlori/gherkin-lint
```

See the [original README](https://github.com/gherkin-lint/gherkin-lint#readme) for CLI usage and the full rule set.

License: [ISC](https://github.com/ohlori/gherkin-lint/blob/cucumber-rule-support/LICENSE)
