# Git Workflow

## Continuous Integration

For Continuous Integration to work, a secret named `NPM_TOKEN` must be added to the repository.

A token can be obtained by logging in to [NPM](https://www.npmjs.com/) and choosing 'Access Tokens' from the avatar drop down.

## Contributor

Checkout a new branch:

```bash
git checkout -b <new-branch>
```

Incrementally make changes, adding and committing using commands like the following. Use an empty commit message, as [commitizen](https://www.npmjs.com/package/commitizen) will prompt for any required commit fields.

```bash
git add -A
git commit -m ""
```

Once changes are finished, create a [changeset](https://www.npmjs.com/package/@changesets/cli). This is interactive. Use the space bar, arrow keys and enter to answer the questions. Use an empty commit message, as [commitizen](https://www.npmjs.com/package/commitizen) will prompt for any required commit fields. Select _docs_ and enter a short description like _add changeset_.

```bash
yarn changeset
git add -A
git commit -m ""
```

Then push the changes. If there is no upstream branch, git will give you an alternative command to run.

```bash
git push
```

From the [GitHub](https://github.com/) UI, create a pull request.
The [Changeset bot](https://github.com/apps/changeset-bot) will confirm the pull request has a changeset in it.

## Maintainer

Review pull requests and once no further changes are necessary, use the [GitHub](https://github.com/) UI to merge, clicking the 'Merge Pull Request' | 'Confirm Merge' buttons.

Merging the pull request will trigger a [changesets release](https://github.com/changesets/action) [action](https://docs.github.com/en/actions), which will create a _Version Packages_ pull request. The _Version Packages_ pull request will manage each package's version, even with additional merges.

When ready to release, use the [GitHub](https://github.com/) UI to merge the _Version Packages_ pull request, clicking the 'Merge Pull Request' | 'Confirm Merge' buttons. Merging the _Version Packages_ pull request will trigger another [changesets release](https://github.com/changesets/action) [action](https://docs.github.com/en/actions), which will bump package versions, publish packages, commit and push changes, and tag the release.
