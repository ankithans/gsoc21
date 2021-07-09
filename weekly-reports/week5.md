# CLI for the CLI framework

## Week 5 Report
- Refactor RuleConfig - remove method implmentations in config structure [#issue110](https://github.com/aerogear/charmil/issues/110) [#105](https://github.com/aerogear/charmil/pull/105)
- Overriding default rules provided by the validator [#issue104](https://github.com/aerogear/charmil/issues/104) [#105](https://github.com/aerogear/charmil/pull/105)
- Regex validation in command name(UseMatches rule) [issue#84](https://github.com/aerogear/charmil/issues/84) [#139](https://github.com/aerogear/charmil/pull/139)
- Set up gh-pages and settings for docusaurus [issue#140](https://github.com/aerogear/charmil/issues/140) [#142](https://github.com/aerogear/charmil/pull/142)
- Config with array of commands during validation [issue#86](https://github.com/aerogear/charmil/issues/86) [#144](https://github.com/aerogear/charmil/pull/144)
    - Skip Commands by mentioning the command path (provided by cobra)
    - Skip Command and it's children/descendants by provding command path
    - Skip commands for particular rule
- Pull pkg from starter to charmil core [issue#149](https://github.com/aerogear/charmil/issues/149) [#154](https://github.com/aerogear/charmil/pull/154)
    - Removes elements that are already in core
    - Swaps some elements with charmil
- Update charmil & validatorOptions in rhoas [#814](https://github.com/redhat-developer/app-services-cli/pull/814)

## Next Week
- Charmil CLI for starter project [issue#143](https://github.com/aerogear/charmil/issues/143) [#155](https://github.com/aerogear/charmil/pull/155)
    - starter example for CLI
    - include charmil validator tests in starter
    - starter go template for CLI files
    - charmil CLI basic structure
    - Adding license, contibuting.md and other no golang stuff
    - charmil CLI init command
- Support for command completion [issue#134](https://github.com/aerogear/charmil/issues/134)
- [Generic flags] Debug [#135](https://github.com/aerogear/charmil/issues/135)
- Extract documentation helpers into charmil core [#136](https://github.com/aerogear/charmil/issues/136)

## Blockers
- config in charmil core