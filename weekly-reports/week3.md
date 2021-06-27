# Let's validate the cobra commands

## Week 3 Report
- Validator for cobra commands(architecture) [#82](https://github.com/aerogear/charmil/pull/82)
  - Length Validator for checking length of provided cobra attributes
  - MustExist Validator to ensure that field in command must exist
  - Provide dev docs for the 2 validators
- Explored some ways to validate the commands [discussion#79](https://github.com/aerogear/charmil/discussions/79)
  - tried to write validator with `go/ast`
- Provided user docs for Logger and i18n
- Add CI/CD and issue & PR templates to repo(CI/CD is incomplete) [#83](https://github.com/aerogear/charmil/pull/83)

## Next Week
Issues to be fixed [issue#58](https://github.com/aerogear/charmil/issues/58), [issue#84](https://github.com/aerogear/charmil/issues/84), [issue#85](https://github.com/aerogear/charmil/issues/85), [issue#86](https://github.com/aerogear/charmil/issues/86)
- Verbose printing while validation [comment-link](https://github.com/aerogear/charmil/pull/82#discussion_r659134180)
  - add related functions in logger and use them while debug printing
- (useMatches) Regex validation in command name [issue#84](https://github.com/aerogear/charmil/issues/84)
- Arguments validators in cobra command [issue#85](https://github.com/aerogear/charmil/issues/85)
- Config with array of commands during validation [issue#86](https://github.com/aerogear/charmil/issues/86)
- Integrate this validator as unit tests in other existing cobra CLI's like rhoas
- User documentation for the Validator library

## Blockers
- How we plan to validate arguments of command [#85](https://github.com/aerogear/charmil/issues/85)
  - handeling duplication/overriding of arguments