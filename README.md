# typescript-project-template

A repo to provide a TypeScript lint &amp; format template.

## Features

- Provide code format using prettier
- Provide code lint using ESlint
- Provide **pre-commit** code lint-check & auto-format using **pretty-quick** & **husky**
- Provide commit message lint using **commitlint**

## Install

If you just clone this repo, note that it is important to prepare **_husky_**

```sh
npm run prepare
```

Make sure the file **commit-msg** and **pre-commit** are executable.
if Not, then run the following commands.

```sh
chmod a+x .husky/commit-msg
chmod a+x .husky/pre-commit
```

## Commands

| Name                 | Desc                                           |
| -------------------- | ---------------------------------------------- |
| npm run prepare      | prepare husky                                  |
| npm run lint         | lint all TypeScript fills                      |
| npm run prettier     | check files whether have code style issues     |
| npm run prettier:fix | re-write the code using prettier format config |
| npm run pretty       | format the staged files                        |

### Commit lint

Commit message should follow the pattern like this

```sh
type(scope?): subject  #scope is optional; multiple scopes are supported (current delimiter options: "/", "\" and ",")
```

**Type Enum**

| Type     | Desc                                          |
| -------- | --------------------------------------------- |
| build    | changes to the build process or related tools |
| chore    | other modify                                  |
| ci       | git ci cd files modified                      |
| docs     | documentation                                 |
| feat     | new feature                                   |
| fix      | bug fix                                       |
| perf     | code performance                              |
| refactor | code refactor                                 |
| revert   | git revert                                    |
| style    | code lint or format                           |
| test     | new test                                      |

## TypeScript config

Should modify the file **tsconfig.json** base on Project.
