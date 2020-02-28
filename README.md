# reproduce-lerna-bug

Repository to reproduce a windows specific bug of lerna 3.16.2 and above

## Description of the bug

The [lerna release v3.16.2](https://github.com/lerna/lerna/releases/tag/v3.16.2) introduces a bug for yarn users on windows.
Symlinks for binaries (in node_modules/.bin) are no longer created.
This bug is not present in v3.16.1 but exists in all newer versions (latest release at time of writing v3.20.2).

Interestingly this behavior only occurs for yarn users, it works fine with npm.

## How to reproduce

1. clone repository
1. `yarn && yarn bootstrap && yarn test-binary-symlink`

will fail.

But changing the lerna version to 3.16.1 (in packge.json) and rerunning the command will work.

## Tested on

- yarn@1.22.0
- node@v12.13.0
- Windows 10 (19041.84)
