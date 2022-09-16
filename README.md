# typescript-project-template

A repo to provide a template about TypeScript lint &amp; format.

## Features

- Provide code format using **prettier**
- Provide code lint using **ESlint**
- Provide **pre-commit** code lint-check & auto-format using **pretty-quick** & **husky**
- Provide commit message lint using **commitlint**
- Provide release version and auto-generated CHANGELOG using **standard-version**

## Install

```sh
npm i
```

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

| Name                 | Desc                                           |     Config      |  Ignore Config  |
| -------------------- | ---------------------------------------------- | :-------------: | :-------------: |
| npm run prepare      | prepare husky                                  |        -        |        -        |
| npm run lint         | code lint                                      | .eslintrc.json  |  .eslintignore  |
| npm run lint:fix     | code lint fix                                  |        -        |        -        |
| npm run prettier     | check files whether have code style issues     | .prettierc.json | .prettierignore |
| npm run prettier:fix | re-write the code using prettier format config |        -        |        -        |
| npm run pretty       | format the staged files                        |        -        |        -        |
| npm run release      | release new version                            |                 |                 |

> Note: [more](#command-release)  
> commmand: **npm run release** will update version in package.json/package-lock.json  
> and will commit it to git. such as [37364c](https://github.com/sanjayheaven/typescript-project-template/commit/37364c602e5209b6ccb3f5cc466cb92ac2fa19d9)

### Commit lint

Commit message should follow the pattern like this

```sh
type(scope?): subject
#scope is optional; multiple scopes are supported (current delimiter options: "/", "\" and ",")
```

**Type Enum**

| Type     | Desc                                            |
| -------- | ----------------------------------------------- |
| build    | changes to the build process or related tools   |
| chore    | other modify                                    |
| ci       | git CI/CD files modified                        |
| docs     | documentation, like docs,README.md,CHANGELOG.md |
| feat     | new feature                                     |
| fix      | bug fix                                         |
| perf     | code performance                                |
| refactor | code refactor                                   |
| revert   | git revert                                      |
| style    | code lint or format                             |
| test     | new test                                        |

### Command Release

**How It Works**

Follow the [Conventional Commits Specification](https://github.com/conventional-changelog/standard-version#:~:text=Conventional%20Commits%20Specification) in your repository.  
When you're ready to release, run standard-version.

**standard-version will then do the following**:

- Retrieve the current version of your repository by looking at package Files, falling back to the last git tag.
- Bump the version based on commits.
- Generates a changelog based on commits
- Creates a new commit including bump Files and updated CHANGELOG.
- Creates a new tag with the new version number.

> Note  
> fix: which represents bug fixes, and correlates to **patch** version.  
> feat: which represents a new feature, and correlates to a **minor** version.  
> feat!:, or fix!:, refactor!:, etc., which represent a breaking change (indicated by the !) and will result in a **major** version.

## Config

There will be different configurations according to different projects.  
After initializing the project, please select the configuration you need according to the project.

Now, in the **examples** directory, there are the following configurations for reference.  
You can directly copy the configuration in the example to the project.

- [x] [React](./examples/React)
- [x] [React-Components](./examples/React-Components)
