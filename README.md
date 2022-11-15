Command line utility that retries `yarn` command when it fails with `the file appears to be corrupt` or `unexpected end of file` error.

This happens quite often for private NPM modules, see https://github.com/yarnpkg/yarn/issues/7521, https://github.com/yarnpkg/yarn/issues/2738

## Installation

	yarn global add @selfagency/yarn-retry

## Usage

From command-line:

	yarn-retry --wait 500 --attempts 10 -- --frozen-lockfile

It has two options: wait (defaults to 500) and attempts (default to 10). Everything after `--` goes directly to yarn, so you can retry e.g. `yarn add`:

	yarn-retry -- add --dev @myorg/my-package --ignore-engines

## Other
Forked from [@artemv/yarn-retry](https://github.com/artemv/yarn-retry). Based on battle-tested [npm-install-retry](https://github.com/jfromaniello/npm-install-retry) utility by José F. Romaniello.
