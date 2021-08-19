<div align="center">
    <a href="https://summerofcode.withgoogle.com/projects/#4595512243650560"><img src="https://cdn.discordapp.com/attachments/852928325197234256/855675167874220032/Group_4.png" width="550" alt="google-summer-of-code"></a>
</div>
<p align="center">
    <code> 
	<a href="#-project-abstract">Project Abstract</a>&nbsp;&nbsp;&nbsp;
    <a href="#-weekly-reports">Weekly Summary</a>&nbsp;&nbsp;&nbsp;
    <a href="#-pull-requests--issues">Pull Requests & Issues</a>&nbsp;&nbsp;&nbsp;
	<a href="#-would-like-to-sync">Would like to sync?</a>&nbsp;&nbsp;&nbsp;
    <a href="#-links">Links</a>
    </code>
</p>
<br>

## ❔ Project Abstract


[Charmil](https://github.com/aerogear/charmil/) is a framework for building command line plugins on top of Golang [Cobra](https://github.com/spf13/cobra) Library.
Charmil will grant your cobra-based CLI superpowers that cobra does not support and that show to be crucial tools for efficiency and effectiveness. These CLI's can also be added to any Host CLI as plugins.


<p align="center">
    <img src="https://raw.githubusercontent.com/aerogear/charmil/main/docs/images/logo_cropped.png">
</p>

Cobra is standard and very famous in the CLI industry and is being used in many industry projects such as Kubernetes, rhoas, gh-cli, etc. To make the development process easier we introduced Charmil.

Charmil solves many problems/issues faced by developers during development of CLI’s. The major feature that Charmil brings on the table is the ability to develop multiple fragmented CLI’s, maintained/working in separate repositories, and later embed/combine them in a single Host CLI.



### Charmil Components in brief
- Charmil SDK - For building mutlirepo CLI’s
- Charmil Validator - Cobra Testing Library
- Charmil CLI - Creating starter and managing CLI project
- Charmil Command Registry - Install CLI plugins with binary from maintained registry

<p align="center">
    <img src="https://github.com/aerogear/charmil/blob/main/docs/images/charmil_pillar.png?raw=true">
</p>

For detailed description visit [Charmil](https://github.com/aerogear/charmil/)

### Charmil Validator
This is the charmil library for testing and controlling many aspects of cobra commands. Like to test react components we have react-testing-library, similar to that to test cobra commands with some given set of customizable rules, we have charmil validator.

Validator provides a customizable set of config attributes, for example -

```go
ruleCfg := rules.ValidatorConfig{
	ValidatorRules: rules.ValidatorRules{
		Length: rules.Length{Limits: map[string]rules.Limit{"Use": {Min: 1}}},
		MustExist: rules.MustExist{Fields: map[string]bool{"Args": true}},
		UseMatches: rules.UseMatches{Regexp: `^[^-_+]+$`},
	},
}
```
Rules provided by validator -

LengthRule
MustExistRule
UseMatchesRule
ExampleMatchesRule
It is recommended to use Charmil Validator while writing unit tests for the cobra commands. Validator can check if the commands are providing proper and latest documentation, length and presence of attributes, regex matching for command names etc. It also provides the feature to skip some command or skip including children for validation.

```go
validationErr := rules.ExecuteRules(cmd, &ruleCfg)
if len(validationErr) != 0 {
	t.Errorf("validationErr was not empty, got length: %d; want %d", len(validationErr), 0)
}
for _, errs := range validationErr {
	if errs.Err != nil {
		t.Errorf("%s: cmd %s: %s", errs.Rule, errs.Cmd.CommandPath(), errs.Name)
	}
}
```

Skipping commands for validation is very easy. To skip a single command just provide the CommandPath and to skip the entire chain of commands(including subcommands/children) use a asterik sign immediately after CommandPath

```go
ValidatorOptions: rules.ValidatorOptions{
	SkipCommands: map[string]bool{"mycli actions*": true},
}
```

Hence validator is very customizable and easy to use for developer productivity! For detailed documentation of charmil validator, visit Charmil Validator Docs

Here is a small diagram to show how is validator working under the hood.

![charmil-validator](https://cdn.discordapp.com/attachments/852928325197234256/866662866265964544/125803970-d47313c8-0bb9-42e9-81aa-ec4367f21634.png)
<br>

## 📅 Weekly Reports
- Week 1️⃣ [Trying to set core in place](weekly-reports/week1.md)
- Week 2️⃣ [Finally there is something to move with](weekly-reports/week2.md)
- Week 3️⃣ [Let's validate the cobra commands](weekly-reports/week3.md)
- Week 4️⃣ [Garnishing charmil validator framework](weekly-reports/week4.md)
- Week 5️⃣ [CLI for the CLI framework](weekly-reports/week5.md)
- Week 6️⃣ [CLI on it's way](weekly-reports/week6.md)
- Week 7️⃣ [Fixing things up](weekly-reports/week7.md)
- Week 8️⃣ [It needs a refactor](weekly-reports/week8.md)
- Week 9️⃣ [Final move before completion](weekly-reports/week9.md)
- Week 1️⃣ 0️⃣ [Case Study](weekly-reports/week10.md)


<br>

## ✨ Pull Requests & Issues

### Repositories

- [aerogear/charmil](https://github.com/aerogear/charmil/)
- [aerogear/charmil-starter](https://github.com/aerogear/charmil-starter)
- [aerogear/charmil-host-example](https://github.com/aerogear/charmil-host-example)
- [aerogear/charmil-plugin-example](https://github.com/aerogear/charmil-plugin-example)
- [redhat-developer/app-services-cli](https://github.com/redhat-developer/app-services-cli)
- [charmil topic on github](https://github.com/topics/charmil)


### Pull Requests Created 

| Pull Request  	| Related Issue  	|
|---	|---	|
| [#45](https://github.com/aerogear/charmil/pull/45) charmil as wrapper for cobra  	        | Charmil Core  	|
| [#48](https://github.com/aerogear/charmil/pull/48) Factory(RHOAS) for driving charmil  	| Charmil Core  	|
| [#52](https://github.com/aerogear/charmil/pull/52) Add i18n support & improve logging  	| [issue#50](https://github.com/aerogear/charmil/issues/50) [#51](https://github.com/aerogear/charmil/issues/51)  	|
| [#82](https://github.com/aerogear/charmil/pull/82) Validator for cobra commands  	| [issue#58](https://github.com/aerogear/charmil/issues/58)  	|
| [#83](https://github.com/aerogear/charmil/pull/83) CI/CD & issue pr templates  	| [issue#53](https://github.com/aerogear/charmil/issues/53)  	|
| [#97](https://github.com/aerogear/charmil/pull/97) fix: traverse all the child cmds + duplicates     | [issue#95](https://github.com/aerogear/charmil/issues/95)  	|
| [#101](https://github.com/aerogear/charmil/pull/101) test for validator & add it to CI/CD   | [issue#94](https://github.com/aerogear/charmil/issues/94) [issue#92](https://github.com/aerogear/charmil/issues/92) 	|
| [#767](https://github.com/redhat-developer/app-services-cli/pull/767) add cobra commands validator in Rhoas   | [issue#777](https://github.com/redhat-developer/app-services-cli/issues/777) |
| [#103](https://github.com/aerogear/charmil/pull/103) validate rules in loop    | [issue#98](https://github.com/aerogear/charmil/issues/98) [issue#93](https://github.com/aerogear/charmil/issues/93) [issue#53](https://github.com/aerogear/charmil/issues/53)|
| [#105](https://github.com/aerogear/charmil/pull/105) refactor RuleConfig + overriding default values   | [issue#110](https://github.com/aerogear/charmil/issues/110) [issue#104](https://github.com/aerogear/charmil/issues/104) [issue#133](https://github.com/aerogear/charmil/issues/133)|
| [#139](https://github.com/aerogear/charmil/pull/139) Regex validation in command name(UseMatches rule)  	        | [issue#84](https://github.com/aerogear/charmil/issues/84)  	|
| [#142](https://github.com/aerogear/charmil/pull/142) Set up gh-pages and settings for docusaurus  	        | [issue#140](https://github.com/aerogear/charmil/issues/140)  	|
| [#144](https://github.com/aerogear/charmil/pull/144) Config with array of commands during validation 	        | [issue#86](https://github.com/aerogear/charmil/issues/86) 	|
| [#154](https://github.com/aerogear/charmil/pull/154) Pull pkg from starter to charmil core  	| [issue#149](https://github.com/aerogear/charmil/issues/149)	|
| [#814](https://github.com/redhat-developer/app-services-cli/pull/814) Update charmil & validatorOptions in rhoas    | Breaking changes in new release |
| [#155](https://github.com/aerogear/charmil/pull/155)   Charmil CLI for starter project       | [issue#143](https://github.com/aerogear/charmil/issues/143)  	|
| [#159](https://github.com/aerogear/charmil/pull/159)   feat: example validation       | [issue#116](https://github.com/aerogear/charmil/issues/116)  	|
| [#160](https://github.com/aerogear/charmil/pull/160)   chore: refactor docs & contributing.md       | [issue#148](https://github.com/aerogear/charmil/issues/148) [issue#126](https://github.com/aerogear/charmil/issues/126) [issue#111](https://github.com/aerogear/charmil/issues/111) [issue#54](https://github.com/aerogear/charmil/issues/54)  	| 
| [#161](https://github.com/aerogear/charmil/pull/161)   fix: skip validation for children       | [issue#151](https://github.com/aerogear/charmil/issues/151)  	|
| [#170](https://github.com/aerogear/charmil/pull/170)   feat: charmil init command       | [issue#165](https://github.com/aerogear/charmil/issues/165) [issue#164](https://github.com/aerogear/charmil/issues/164)  	|
| [#173](https://github.com/aerogear/charmil/pull/173)   chore: remove starter from main       | Charmil Core  	|
| [#182](https://github.com/aerogear/charmil/pull/182)   feat: Punctuation rule in validator       | [issue#168](https://github.com/aerogear/charmil/issues/168)  	|
| [#188](https://github.com/aerogear/charmil/pull/188)   chore: refactor repo structure       | [issue#180](https://github.com/aerogear/charmil/issues/180)  	|
| [#860](https://github.com/aerogear/charmil/pull/860)   docs: remove full stops from flags       | [issue#830](https://github.com/aerogear/charmil/issues/830)  	|
| [#193](https://github.com/aerogear/charmil/pull/193)   fix: goreleaser build path       |  Build issue 	|
| [#195](https://github.com/aerogear/charmil/pull/195)   chore: move factory to starter       | [issue#162](https://github.com/aerogear/charmil/issues/162)  	|
| [#201](https://github.com/aerogear/charmil/pull/201)   fix: update starter url and imports       | Charmil Init Command  	|
| [#900](https://github.com/aerogear/charmil/pull/900)   fix: locale key err in cluster_kubernetes       | [issue#899](https://github.com/aerogear/charmil/issues/899)  	|
| [#202](https://github.com/aerogear/charmil/pull/202)   feat: disable validation rule option       | [issue#197](https://github.com/aerogear/charmil/issues/197)  	|
| [#203](https://github.com/aerogear/charmil/pull/203)   feat: check for updates in starter       | [issue#138](https://github.com/aerogear/charmil/issues/138)  	|
| [#207](https://github.com/aerogear/charmil/pull/207)   feat: add command in charmil cli        | [issue#166](https://github.com/aerogear/charmil/issues/166)  	|
| [#209](https://github.com/aerogear/charmil/pull/209)   docs: update i18n docs       | [issue#163](https://github.com/aerogear/charmil/issues/163)  	|
| [#219](https://github.com/aerogear/charmil/pull/219)   chore: refactor core package       | [issue#213](https://github.com/aerogear/charmil/issues/213) [issue#183](https://github.com/aerogear/charmil/issues/183) [issue#185](https://github.com/aerogear/charmil/issues/185)  	|
| [#223](https://github.com/aerogear/charmil/pull/202)   feat: example builder utility       | [issue#218](https://github.com/aerogear/charmil/issues/218)  	|





<br>

## 🔄 Would like to sync?
- We are keeping all the communications open, so that everyone can sync and is free to contribute. So if you have any feature/bugs suggestions about anything please donot hesitate to open up an [issue](https://github.com/aerogear/charmil/issues/new)
- You can join [Aerogear's discord server](https://discord.gg/hsDJUPkAWH) to participate in the discussions happening

<br>

## 🔗 Links
- [Charmil Github Repository](https://github.com/aerogear/charmil/)
- [My Blog](https://ankithans.github.io)

<br>
