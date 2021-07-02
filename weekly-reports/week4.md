# Garnishing charmil validator framework

## Week 4 Report
- Rule Executor for rules, rules only return validationErrors, all the heavy lifting of traversing commands and subcommands done by RuleExecutor [issue#89](https://github.com/aerogear/charmil/issues/89)
- Fix Traversing and duplication issue in validation [#97](https://github.com/aerogear/charmil/pull/97)
- Write test for validator & add it to CI/CD [#101](https://github.com/aerogear/charmil/pull/101)
- Use validator in [Rhoas CLI](https://github.com/redhat-developer/app-services-cli) for testing cobra commands [#767](https://github.com/redhat-developer/app-services-cli/pull/767)
- Refactor rules to implement Rules interface [#103](https://github.com/aerogear/charmil/pull/103) [issue98](https://github.com/aerogear/charmil/issues/98)

## Next Week
- Refactor RuleConfig in validator API to accept slice of RuleInterface, instead of hardcoding every rule in RuleConfig [#issue110](https://github.com/aerogear/charmil/issues/110) [#105](https://github.com/aerogear/charmil/pull/105) 
- Overriding default rules provided by the validator [#105](https://github.com/aerogear/charmil/pull/105) [#issue104](https://github.com/aerogear/charmil/issues/104)
- Regex validation in command name(UseMatches rule) [issue#84](https://github.com/aerogear/charmil/issues/84)
- Arguments Validator for cobra commands [issue#85](https://github.com/aerogear/charmil/issues/85)
- Config with array of commands during validation [#issue86](https://github.com/aerogear/charmil/issues/86)

## Blockers
- Merging of default rules array and rules provided by user(during [#issue110](https://github.com/aerogear/charmil/issues/110)