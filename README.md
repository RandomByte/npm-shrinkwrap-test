# npm-shrinkwrap-test

## Steps to reproduce

1. `git clone git@github.com:RandomByte/npm-shrinkwrap-test.git && cd npm-shrinkwrap-test`
2. `npm install`
3. Check for a known devDependency and notice that it has been installed:
	```
	npm ls -a | grep 'ava'
	> ├─┬ ava@3.15.0 extraneous
	```
4. `npm prune --production` removes the `ava` package. But a following `npm install` will install it again