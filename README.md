# npm-shrinkwrap-test

Showcase for issue https://github.com/npm/cli/issues/4323

## Steps to reproduce

This package has a dependency to `@ui5/cli` in version `^3.0.0-alpha.1`. A known devDependency of `@ui5/cli` is `ava`. This, as well as other devDependencies are unexpectedly installed, even though they are marked as `"dev": true` in the npm-shrinkwrap.json of `@ui5/cli`.

1. `git clone git@github.com:RandomByte/npm-shrinkwrap-test.git && cd npm-shrinkwrap-test`
2. `npm install`
3. Check for a known devDependency and notice that it has been installed:
	```
	npm ls -a | grep 'ava'
	> ├─┬ ava@3.15.0 extraneous
	```
4. `npm prune --production` removes the `ava` package. But a following `npm install` will install it again