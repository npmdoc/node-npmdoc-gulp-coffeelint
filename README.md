# api documentation for  [gulp-coffeelint (v0.6.0)](https://github.com/janraasch/gulp-coffeelint#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-coffeelint.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-coffeelint) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-coffeelint.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-coffeelint)
#### Lint your CoffeeScript using gulp and CoffeeLint

[![NPM](https://nodei.co/npm/gulp-coffeelint.png?downloads=true)](https://www.npmjs.com/package/gulp-coffeelint)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-coffeelint_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-coffeelint/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jan Raasch",
        "email": "jan@janraasch.com",
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
            "name": "janraasch",
            "email": "jan@janraasch.com"
        }
    ],
    "name": "gulp-coffeelint",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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
    "version": "0.6.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-coffeelint](#apidoc.module.gulp-coffeelint)
1.  [function <span class="apidocSignatureSpan">gulp-coffeelint.</span>reporter (type)](#apidoc.element.gulp-coffeelint.reporter)
1.  object <span class="apidocSignatureSpan">gulp-coffeelint.</span>utils

#### [module gulp-coffeelint.utils](#apidoc.module.gulp-coffeelint.utils)
1.  [function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>createPluginError (message)](#apidoc.element.gulp-coffeelint.utils.createPluginError)
1.  [function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>formatOutput (errorReport, opt, literate)](#apidoc.element.gulp-coffeelint.utils.formatOutput)
1.  [function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>isLiterate (file)](#apidoc.element.gulp-coffeelint.utils.isLiterate)



# <a name="apidoc.module.gulp-coffeelint"></a>[module gulp-coffeelint](#apidoc.module.gulp-coffeelint)

#### <a name="apidoc.element.gulp-coffeelint.reporter"></a>[function <span class="apidocSignatureSpan">gulp-coffeelint.</span>reporter (type)](#apidoc.element.gulp-coffeelint.reporter)
- description and source-code
```javascript
reporter = function (type) {
  if (type === 'fail') {
    return failReporter();
  }
  if (type === 'failOnWarning') {
    return failOnWarningReporter();
  }
  if (type == null) {
    type = 'coffeelint-stylish';
  }
  reporter = loadReporter(type);
  if (typeof reporter !== 'function') {
    throw createPluginError(type + " is not a valid reporter");
  }
  return reporterStream(reporter);
}
```
- example usage
```shell
...
'''javascript
var gulp = require('gulp');
var coffeelint = require('gulp-coffeelint');

gulp.task('lint', function () {
    gulp.src('./src/*.coffee')
        .pipe(coffeelint())
        .pipe(coffeelint.reporter())
});
'''

## API

### 'coffeelint([optFile,] [opt,] [literate,] [rules])'
All arguments are optional. By default 'gulp-coffeelint' will walk up the directory tree looking for a 'coffeelint.json' (per file
, i.e. dirname) or a 'package.json' that has a 'coffeelintConfig' object ([as the cli does](http://www.coffeelint.org/#usage)).
Also, '.litcoffee' and '.coffee.md' files will be treated as Literate CoffeeScript.
...
```



# <a name="apidoc.module.gulp-coffeelint.utils"></a>[module gulp-coffeelint.utils](#apidoc.module.gulp-coffeelint.utils)

#### <a name="apidoc.element.gulp-coffeelint.utils.createPluginError"></a>[function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>createPluginError (message)](#apidoc.element.gulp-coffeelint.utils.createPluginError)
- description and source-code
```javascript
createPluginError = function (message) {
  return new PluginError('gulp-coffeelint', message);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-coffeelint.utils.formatOutput"></a>[function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>formatOutput (errorReport, opt, literate)](#apidoc.element.gulp-coffeelint.utils.formatOutput)
- description and source-code
```javascript
formatOutput = function (errorReport, opt, literate) {
  var errorCount, ref, warningCount;
  ref = errorReport.getSummary(), errorCount = ref.errorCount, warningCount = ref.warningCount;
  return {
    success: errorCount === 0,
    results: errorReport,
    errorCount: errorCount,
    warningCount: warningCount,
    opt: opt,
    literate: literate
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-coffeelint.utils.isLiterate"></a>[function <span class="apidocSignatureSpan">gulp-coffeelint.utils.</span>isLiterate (file)](#apidoc.element.gulp-coffeelint.utils.isLiterate)
- description and source-code
```javascript
isLiterate = function (file) {
  return /\.(litcoffee|coffee\.md)$/.test(file);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
