# Garnishing charmil validator framework

## Week 4 Report
- Rule Executor for rules, rules only return validationErrors, all the heavy lifting of traversing commands and subcommands done by RuleExecutor [issue#89](https://github.com/aerogear/charmil/issues/89) [#82](https://github.com/aerogear/charmil/pull/82)
- Fix Traversing and duplication issue in validation [issue#95](https://github.com/aerogear/charmil/issues/95) [#97](https://github.com/aerogear/charmil/pull/97)
- Write test for validator & add it to CI/CD [issue#94](https://github.com/aerogear/charmil/issues/94) [#101](https://github.com/aerogear/charmil/pull/101)
- Use validator in [Rhoas CLI](https://github.com/redhat-developer/app-services-cli) for testing cobra commands [issue#777](https://github.com/redhat-developer/app-services-cli/issues/777) [#767](https://github.com/redhat-developer/app-services-cli/pull/767)
- Refactor rules to implement Rules interface [issue#98](https://github.com/aerogear/charmil/issues/98) [#103](https://github.com/aerogear/charmil/pull/103)

## Next Week
- Refactor RuleConfig in validator API to accept slice of RuleInterface, instead of hardcoding every rule in RuleConfig [#issue110](https://github.com/aerogear/charmil/issues/110) [#105](https://github.com/aerogear/charmil/pull/105) 
- Overriding default rules provided by the validator [#issue104](https://github.com/aerogear/charmil/issues/104) [#105](https://github.com/aerogear/charmil/pull/105) 
- Regex validation in command name(UseMatches rule) [issue#84](https://github.com/aerogear/charmil/issues/84)
- Arguments Validator for cobra commands [issue#85](https://github.com/aerogear/charmil/issues/85)
- Config with array of commands during validation [#issue86](https://github.com/aerogear/charmil/issues/86)

## Blockers
- Merging of default rules array and rules provided by user(during [#issue110](https://github.com/aerogear/charmil/issues/110)