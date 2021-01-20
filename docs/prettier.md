This repo uses the npm package [Prettier](https://prettier.io/) to automatically format your JavaScript code for you, so you don't have to think about how you format your code, and code reviewers don't have to worry about looking for formatting issues. To make Prettier easier to adopt, it is also added as a _pre-commit hook_, meaning it will run in the background whenever you create a git commit.

## Try it out

If you want to try the pre-commit hook, run `npm install`, make an egregiously formatted change to a javascript/css/markdown file, and try to commit it. Note that the commit will fail if Prettier is just undoing your change, so you'll have to make a non-trivial change.

## How this was implemented

The directions from [Prettier's documentation](https://prettier.io/docs/en/install.html) were followed with little modification.

It boils down to installing an **exact** version of Prettier to the development environment (you wouldn't want developers to install other versions of Prettier with potentially conflicting style rules): `npm install --save-dev --save-exact prettier`

And adding a configuration file: `echo {}> .prettierrc.json`

Note that I intentionally skipped creating a `.prettierignore` file. It is possible to reuse the `.gitignore` file for Prettier when running it manually (if it ever needs to be run manually), which avoids the issue of the two files getting out of sync.

Instructions for installing `lint-staged` are [here](https://prettier.io/docs/en/precommit.html). This installs the pre-commit hook that runs Prettier before every commit.

## Caveats and future considerations

- While Prettier automatically formats code, it does not fail CI if code is improperly formatted.
- For the pre-commit hook to be installed, you must first run `npm install`. This is something contributors should do anyway, but it's possible to miss this step, especially since code style is not enforced by CI.
- This currently only impacts javascript/css/markdown files. Do similar tools exist for Java?
- The pre-commit hook is currently managed by installing an npm package in the `/javascript` folder, since pre-commit hooks cannot be added directly to a repo. Does this approach make sense for running pre-commit hooks on code outside of the `/javascript` folder?
