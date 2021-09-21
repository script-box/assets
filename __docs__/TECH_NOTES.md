# script-box.assets

> script-box assets.

## Technical Notes

<!-- DEV-NOTES -->

<!-- add dev notes -->

<!-- /DEV-NOTES -->

### script-box/configure

[script-box/configure](https://www.npmjs.com/package/@script-box/configure.cli) is used to configure this solution.

Run the command `yarn configure` to configure the solution.

Run the command `yarn setup` to configure, add git hooks, document and format the solution.

It will configure the tools used by this solution, such as:

- [Commitizen](https://www.npmjs.com/package/commitizen)
- [Depcheck](https://www.npmjs.com/package/depcheck)
- [git](https://git-scm.com/)
- [Husky](https://www.npmjs.com/package/husky)
- [lint-staged](https://www.npmjs.com/package/lint-staged)
- [Prettier](https://prettier.io/)
- [script-box/configure](https://www.npmjs.com/package/@script-box/configure.cli)
- [script-box/document](https://www.npmjs.com/package/@script-box/document.cli)
- [VS Code](https://code.visualstudio.com/)

### Dependency Checking

Run the command `yarn depcheck` to check dependencies using [Depcheck](https://www.npmjs.com/package/depcheck).

### Document

Run the command `yarn document` to generate documentation using [script-box/document](https://www.npmjs.com/package/@script-box/document.cli).

### Format

Run the command `yarn format` to format code/artefacts using [Prettier](https://prettier.io/).

### Git Hooks

Run the command `yarn githooks` to setup:

- a pre-commit git hook to run [lint-staged](https://www.npmjs.com/package/lint-staged) which will format the code using [Prettier](https://prettier.io/).
- a prepare-commit-msg git hook to run [Commitizen](https://www.npmjs.com/package/commitizen) to prompt for a standard commit message.
