# CHANGELOG

## 1.0.0-rc.15

* Update docs

## 1.0.0-rc.14

* Make `--no-verify` message more accurate and only show it for hooks that can be skipped
* Improve error messages

## 1.0.0-rc.13

* Show a message when Node can't be found in PATH

## 1.0.0-rc.12

* Fix exit code when used with unsupported Node version
* Update dependencies

## 1.0.0-rc.11

* Show a message instead of crashing if Node version is unsupported by Husky

## 1.0.0-rc.10

* Fix `HUSKY_GIT_PARAMS` containing only the first Git param

## 1.0.0-rc.9

* If `node_modules/husky` is missing, show message but do not crash
* Remove and upgrade some `dependencies`

## 1.0.0-rc.8

* Add `HUSKY_GIT_STDIN` environment variable for `pre-push`, `pre-receive`, `post-receive` and `post-rewrite` to access arguments passed by Git via stdin.

## 1.0.0-rc.7

* Update `cosmiconfig` dependency
* Fix `package.json` normalization error

## 1.0.0-rc.6

* Fix install error with `pnpm`

## 1.0.0-rc.5

* Auto migrate `yorkie` hooks 

## 1.0.0-rc.4

* Re-enable Git submodule and worktree support

## 1.0.0-rc.3

* Re-enable subdirectory support

## 1.0.0-rc.2

* Upgrade `run-node` dependency

## 1.0.0-rc.1

* Namespace environment variable created by husky
  * `GIT_PARAMS` becomes `HUSKY_GIT_PARAMS`
* Starting also with `1.0.0` versioning

## 0.15.0-rc.13

* Revert `GIT_STDIN` for the moment. Needs more testing.

`rc.10`, `rc.11` and `rc.12` are broken for some GUI clients due to `read` command

## 0.15.0-rc.9

* Handle case where `.git/hooks` directory doesn't exit

## 0.15.0-rc.8

* Handle case where `v0.14` git hooks wouldn't have been uninstalled

## 0.15.0-rc.7

* Move `postinstall` script to `install`
* Fix line ending error when running `upgrader` from OS X/Linux

## 0.15.0-rc.6

* Fix `[[` error

## 0.15.0-rc.5

* Fix error with GitHub Desktop on Windows

## 0.15.0-rc.4

* Catch error if `git` command fails

## 0.15.0-rc.3

* Fix `husky-upgrade`
* Drop `Node 4` support

## 0.15.0-rc.2

* Fix install error

## 0.15.0-rc.1

* `sendemail-validate` hook [#173](https://github.com/typicode/husky/pull/173)
* `HUSKY_SKIP_INSTALL` environment variable for skipping git hooks installation [#178](https://github.com/typicode/husky/pull/178)
* `.huskyrc` config [#209](https://github.com/typicode/husky/pull/209)
* `pnpm` support
* Support environments where `yarn` is the only package manager installed
* Move config from `scripts` field to `husky` field
* Prefer raw names for Git hooks (`pre-commit` rather than `precommit`)
* Drop integrated `nvm` support
* To ease upgrade:
  * Provide `husky-upgrade` command
  * Add deprecation warning for hooks that are defined in `scripts` (but still run them)

## 0.14.3

* Fix handle space in `PATH` [#150](https://github.com/typicode/husky/pull/114)

## 0.14.2

* Fix handle space in `HOME`

## 0.14.1

* Fix Git hooks install on Windows
* Fix hook script when `nvm` was installed with Brew

## 0.14.0

* Fix `npm@5` `Error: Cannot find module` warning when uninstalling
* Drop `Node 0.12` support
* Don't reload `nvm` if it's already in `PATH`
* Add Git worktree support [#114](https://github.com/typicode/husky/pull/114)
* Hide irrelevant `--no-verify` message for `prepare-commit-msg` [#137](https://github.com/typicode/husky/issues/137)

## 0.13.4

* Add Node version to husky output

## 0.13.3

* Revert `Fixes issue with OS X + brew where nvm was loaded even when npm was already present` that was introduced in `v0.13.0` as it was preventing Husky to load `nvm` in some cases [#106](https://github.com/typicode/husky/issues/106)

## 0.13.2

* Fixes issue [#103](https://github.com/typicode/husky/issues/103)

## 0.13.1

* Makes it easier for projects to transition from [ghooks](https://github.com/gtramontina/ghooks) by detecting ghooks installed scripts and automatically migrating them

## 0.13.0

* Makes `husky` a little less verbose by default
* Fixes issue with `OS X + brew` where `nvm` was loaded even when `npm` was already present
* Fixes issue with Git `v1.9` on Windows
* Prevents Git hooks being installed when husky is in a sub `node_modules` directory (i.e. `./node_modules/A/node_modules/husky`)

## 0.12.0

* Adds Git submodule support
* Adds Cygwin support
* Improves edge cases support (`.git` not found and `git` not in `PATH`)
* If `npm` is already present in path, doesn't load `nvm` default or `.nvmrc` version, which makes things faster in terminal. In GUI apps, the behavior is unchanged.
