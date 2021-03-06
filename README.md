[![Travis](https://img.shields.io/travis/mediamonks/seng-browser.svg?maxAge=2592000)](https://travis-ci.org/mediamonks/seng-browser)
[![Code Climate](https://img.shields.io/codeclimate/github/mediamonks/seng-browser.svg?maxAge=2592000)](https://codeclimate.com/github/mediamonks/seng-browser)
[![Coveralls](https://img.shields.io/coveralls/mediamonks/seng-browser.svg?maxAge=2592000)](https://coveralls.io/github/mediamonks/seng-browser?branch=master)
[![npm](https://img.shields.io/npm/v/seng-browser.svg?maxAge=2592000)](https://www.npmjs.com/package/seng-browser)
[![npm](https://img.shields.io/npm/dm/seng-browser.svg?maxAge=2592000)](https://www.npmjs.com/package/seng-browser)

# seng-browser

Add a description here...


## Installation

```sh
npm i -S seng-browser
```

Or grab one of the following files from the `/dist/` folder for manual use:

- **umd** (bundled with webpack)
- **amd** (bundled with webpack)
- **commonjs2** (bundled with webpack, but why don't you use npm?)
- **browser** (bundled with webpack, available as `window.SengBoilerplate`)
- **system**
- **es6**

## Usage

```ts
import SengBoilerplate from 'seng-browser';
// import SengBoilerplate from 'seng-browser/lib/classname';

// do something with SengBoilerplate
```


## Documentation

View the [generated documentation](https://rawgit.com/MediaMonks/seng-browser/master/doc/typedoc/index.html).


## Building

In order to build seng-browser, ensure that you have [Git](http://git-scm.com/downloads)
and [Node.js](http://nodejs.org/) installed.

Clone a copy of the repo:
```sh
git clone https://github.com/MediaMonks/seng-browser.git
```

Change to the seng-browser directory:
```sh
cd seng-browser
```

Install dev dependencies:
```sh
npm install
```

Use one of the following main scripts:
```sh
npm run build   		# build this project
npm run generate   		# generate all artifacts (compiles ts, webpack, docs and coverage)
npm run typings			# install .d.ts dependencies (done on install)
npm run test-unit    	# run the unit tests
npm run validate		# runs validation scripts, including test, lint and coverage check
npm run lint			# run tslint on this project
npm run doc				# generate typedoc and yuidoc documentation
npm run typescript-npm	# just compile the typescript output used in the npm module
```

When installing this module, it adds a pre-commit hook, that runs the `validate`
script before committing, so you can be sure that everything checks out.

## Contribute

View [CONTRIBUTING.md](./CONTRIBUTING.md)


## Changelog

View [CHANGELOG.md](./CHANGELOG.md)


## Authors

View [AUTHORS.md](./AUTHORS.md)


## LICENSE

[MIT](./LICENSE) © MediaMonks


## About this browser

**Remove this section when cloning this browser to a real project!**

### Folders

This browser contains the following folders:
* **/config** - Contains the config files for karma and webpack
* **/coverage** - Contains the generated test code coverage, is sent to Code
Climage and Coveral.io.
* **/dist** - Contains the compiled code in different forms for manual usage.
* **/doc** - Can contain additional documentation.
* **/docs/typedoc/** - Contains the generated documentation by typedoc. (Can be
removed for JS-only project)
* **/docs/yuidoc/** - Contains the generated documentation by yuidoc. (Can be
removed for TS-only project)
* **/example** - Can contain additional examples on how to use this module.
* **/lib** - Contains the built code from `src/lib`, will be published to npm.
* **/node_modules** - Contains the node modules generated by running `npm i`.
* **/script** - Contains scripts being called from npm scripts.
* **/src** - Contains the source code.
* **/test** - Contains the tests.
* **/typings** - Contains the .d.ts files generated by running `typings i`.
* **/vendor** - Can contain 3rd party code used in this project, when not
available on npm.

### Files

This browser contains the following files:
* **/config/karma.conf.js** - Configuration for Karma test runner.
* **/config/webpack.conf.js** - Configuration for Webpack builds.
* **/script/webpack.js** - Creates all the different webpack dist builds.
* **.codeclimate.yml** - The Code Climate configuration for this project.
* **.editorconfig** - Defines general formatting rules.
* **.gitignore** - These files should not end up in git.
* **.npmignore** - These files should not end up in npm.
* **.travis.yml** - Configuration for Travis CI.
* **AUTHORS.md** - Contains a list of all the authors that worked on this module.
* **CONTRIBUTING.md** - Contains information on how to contribute on this project.
* **index.d.ts** - The built Typescript definitions, referenced in the package.json.
Will be published to npm.
* **index.d.ts** - The built Typescript index, referenced in the package.json.
Will be published to npm.
* **LICENSE** - Our license file.
* **package.json** - To list the npm package information, all the dependencies,
and contains all the scripts that can be run.
* **README.MD** - This file, remove the about section when cloning this browser.
* **tsconfig.json** - The TypeScript configuration file for this project.
* **/test/tsconfig.json** - The TypeScript configuration file for the tests.
* **tslint.json** - The linting rules for our TypeScript code.
* **typings.json** - The .d.ts dependencies for this project.

### TypeScript

Todo: describe TypeScript configuration and usage.

### Karma

Todo: describe Karma configuration and usage.

### TSLint

Todo: describe TSLint configuration and usage.

### TypeDoc

Todo: describe TypeDoc configuration and usage.

### Travis

This project uses [Travis](https://travis-ci.org] to build, test and
publish its code to npm. Travis is free for public Github repositories.

It runs on all commits, shows the build status for pull requests, and
publishes to npm when a new tag/release is created.

Travis only runs the `npm test` script, so have configured that script
to run everything we want Travis to check. Besides the unit tests, we
also run our validations and linters.

The travis configuration is placed in a `.travis.yml` file, consisting
of multiple sections.

1.  Defines the `node_js` [language](https://docs.travis-ci.com/user/languages/javascript-with-nodejs),
    and tells travis on which node versions to run the process.
2.  Before running, it needs to install some global dependencies, and
    when it processes some coverage results.
3.  It can do a [npm deploy](https://docs.travis-ci.com/user/deployment/npm),
    telling it to keep the generated artifacts and only publish when run
    on node 4 and when a tag was committed. It also contains the email
    address and api key of the npm user.
4.  Code Climate has a [travis plugin](https://docs.travis-ci.com/user/code-climate/)
    that automatically uploads the code coverage results.

Because we want to keep the npm api key secret, we generate a secure
token with the [Travis Client](https://github.com/travis-ci/travis.rb),
a CLI written in ruby.

Before we can do this, we must make sure that the repository is added
to Travis, because Travis needs the repository owner/name info to make
sure the encrypted values only work for that repository. 

1.  First you need to [login](https://github.com/travis-ci/travis.rb#login)
    with your travis account:
    
    ```sh
    $ travis login
    ```
    
    To verify that you are logged in correctly you can check:
    
    ```sh
    $ travis whoami
    ```
    
2.  Then make sure you are logged in to your npm account with the
    [adduser](https://docs.npmjs.com/cli/adduser) command:
    
    ```sh
    $ npm adduser
    ```
    
    To verify that you are logged in correctly you can check:
        
    ```sh
    $ npm whoami
    ```
    
3.  Now we need to grab your auth token so we can encrypt it:
    
    ```sh
    $ cat ~/.npmrc
    
    # outputs:
    //registry.npmjs.org/:_authToken=<your_auth_token>
    ```
    
4.  Then let's encrypt that token using the travis [encrypt](https://github.com/travis-ci/travis.rb#encrypt)
    command:
    
    ```sh
    $ travis encrypt <your_auth_token>
    Detected repository as mediamonks/seng-browser, is this correct? |yes|
    Please add the following to your .travis.yml file:
    
      secure: "YcN...Zb="
    ```
    
    Now copy that last line, paste it into your `.travis.yml`, and make
    sure it looks something like this:
    
    ```yml
    deploy:
      provider: npm
      email: "john@doe.com"
      api_key:
        secure: "YcN...Zb="
    ```

### Code Climate

Todo: describe Code Climate configuration and usage.

### Coverall

Todo: describe Coverall configuration and usage.

### NPM

Todo: describe NPM configuration and usage.
