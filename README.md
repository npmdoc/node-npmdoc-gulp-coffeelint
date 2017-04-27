# npmdoc-gulp-coffeelint

#### basic api documentation for  [gulp-coffeelint (v0.6.0)](https://github.com/janraasch/gulp-coffeelint#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-coffeelint.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-coffeelint) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-coffeelint.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-coffeelint)

#### Lint your CoffeeScript using gulp and CoffeeLint

[![NPM](https://nodei.co/npm/gulp-coffeelint.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gulp-coffeelint)

- [https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jan Raasch",
        "url": "http://janraasch.com"
    },
    "bugs": {
        "url": "https://github.com/janraasch/gulp-coffeelint/issues"
    },
    "dependencies": {
        "args-js": "^0.10.5",
        "coffeelint": "^1.4.0",
        "coffeelint-stylish": "^0.1.1",
        "gulp-util": "^3.0.0",
        "through2": "^2.0.0"
    },
    "description": "Lint your CoffeeScript using gulp and CoffeeLint",
    "devDependencies": {
        "coffee-script": "^1.7.1",
        "coffeelint-use-strict": "^1.0.0",
        "conventional-changelog": "^0.5.0",
        "coveralls": "^2.8.0",
        "del": "^2.0.1",
        "gulp": "^3.5.2",
        "gulp-coffee": "^2.1.2",
        "istanbul": "^0.4.0",
        "mocha": "^2.1.0",
        "proxyquire": "^1.4.0",
        "should": "^8.0.0",
        "sinon": "^1.8.1"
    },
    "directories": {},
    "dist": {
        "shasum": "b4706849c5e3b057658bf638ccfa5dee7351023b",
        "tarball": "https://registry.npmjs.org/gulp-coffeelint/-/gulp-coffeelint-0.6.0.tgz"
    },
    "engines": {
        "node": ">=0.10.0",
        "npm": ">=1.3.7"
    },
    "files": [
        "index.js",
        "lib/*.js"
    ],
    "gitHead": "2a01b0aae93c24af1e2ca7e19569f1405951fade",
    "homepage": "https://github.com/janraasch/gulp-coffeelint#readme",
    "keywords": [
        "gulpplugin",
        "lint",
        "coffee",
        "coffeelint",
        "coffeescript",
        "coffee-script",
        "codeconventions"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "janraasch"
        }
    ],
    "name": "gulp-coffeelint",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/janraasch/gulp-coffeelint.git"
    },
    "scripts": {
        "changelog": "conventional-changelog -p angular -i changelog.md -w",
        "coveralls": "cat ./coverage/lcov.info | ./node_modules/coveralls/bin/coveralls.js",
        "prepublish": "gulp coffee --require \"coffee-script/register\"",
        "test": "coffeelint gulpfile.coffee index.coffee lib test -f ./coffeelint.json && istanbul test _mocha --report lcovonly -- ./test/*.coffee --require coffee-script/register --reporter spec"
    },
    "version": "0.6.0",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
