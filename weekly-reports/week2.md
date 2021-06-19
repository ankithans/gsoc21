# Finally there is something to move with

## Week 2 Report
- Use Factory from [RHOAS](https://github.com/redhat-developer/app-services-cli/) to deliver features over cobra [#48](https://github.com/aerogear/charmil/pull/48)
- Implement Logger for unified logging experience [#48](https://github.com/aerogear/charmil/pull/48) [#52](https://github.com/aerogear/charmil/pull/52)
- Add internationalization support for the plugins [#52](https://github.com/aerogear/charmil/pull/52)
- Provide API docs for logger and i18n [#52](https://github.com/aerogear/charmil/pull/52)
- Create [Issues](https://github.com/aerogear/charmil/issues) for the potential features in charmil

## Next Week
- POC for validation of commands [issue#58](https://github.com/aerogear/charmil/issues/58)
- Research on more validation methods for arguments in addition to what cobra provides [issue#68](https://github.com/aerogear/charmil/issues/68)
- Provide User Documentation for logging, i18n and further features

## Blockers
- Enhancing UX of the Library: Need to figure out the ways to improve the Developer experience [related comment](https://github.com/aerogear/charmil/pull/52#issuecomment-863791549), [discussion#57](https://github.com/aerogear/charmil/discussions/57)
- Factory is an interface to include the features into the CLI(which is temporary), taken form [RHOAS](https://github.com/redhat-developer/app-services-cli/). Find other ways to improve the core. But this doesn't affect the development of features directly.