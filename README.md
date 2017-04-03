# api documentation for  [xhr (v2.4.0)](https://github.com/naugtur/xhr)  [![npm package](https://img.shields.io/npm/v/npmdoc-xhr.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-xhr) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-xhr.svg)](https://travis-ci.org/npmdoc/node-npmdoc-xhr)
#### small xhr abstraction

[![NPM](https://nodei.co/npm/xhr.png?downloads=true)](https://www.npmjs.com/package/xhr)

[![apidoc](https://npmdoc.github.io/node-npmdoc-xhr/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-xhr_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-xhr/build..beta..travis-ci.org/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-xhr/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-xhr/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Raynos",
        "email": "raynos2@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/naugtur/xhr/issues",
        "email": "naugtur@gmail.com"
    },
    "contributors": [
        {
            "name": "Jake Verbaten"
        },
        {
            "name": "Zbyszek Tenerowicz",
            "email": "naugtur@gmail.com"
        }
    ],
    "dependencies": {
        "global": "~4.3.0",
        "is-function": "^1.0.1",
        "parse-headers": "^2.0.0",
        "xtend": "^4.0.0"
    },
    "description": "small xhr abstraction",
    "devDependencies": {
        "for-each": "^0.3.2",
        "pre-commit": "1.0.10",
        "run-browser": "github:naugtur/run-browser",
        "tap-spec": "^4.0.2",
        "tape": "^4.0.0"
    },
    "directories": {},
    "dist": {
        "shasum": "e16e66a45f869861eeefab416d5eff722dc40993",
        "tarball": "https://registry.npmjs.org/xhr/-/xhr-2.4.0.tgz"
    },
    "gitHead": "a7b434418b6164a5e23439c5bb7466e5f82d457e",
    "homepage": "https://github.com/naugtur/xhr",
    "keywords": [
        "xhr",
        "http",
        "xmlhttprequest",
        "xhr2",
        "browserify"
    ],
    "license": "MIT",
    "main": "index",
    "maintainers": [
        {
            "name": "raynos",
            "email": "raynos2@gmail.com"
        },
        {
            "name": "naugtur",
            "email": "naugtur@gmail.com"
        }
    ],
    "name": "xhr",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/naugtur/xhr.git"
    },
    "scripts": {
        "browser": "run-browser -m test/mock-server.js test/index.js",
        "test": "run-browser test/index.js -b -m test/mock-server.js | tap-spec"
    },
    "version": "2.4.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module xhr](#apidoc.module.xhr)
1.  [function <span class="apidocSignatureSpan">xhr.</span>XMLHttpRequest ()](#apidoc.element.xhr.XMLHttpRequest)
1.  [function <span class="apidocSignatureSpan">xhr.</span>del (uri, options, callback)](#apidoc.element.xhr.del)
1.  [function <span class="apidocSignatureSpan">xhr.</span>get (uri, options, callback)](#apidoc.element.xhr.get)
1.  [function <span class="apidocSignatureSpan">xhr.</span>head (uri, options, callback)](#apidoc.element.xhr.head)
1.  [function <span class="apidocSignatureSpan">xhr.</span>patch (uri, options, callback)](#apidoc.element.xhr.patch)
1.  [function <span class="apidocSignatureSpan">xhr.</span>post (uri, options, callback)](#apidoc.element.xhr.post)
1.  [function <span class="apidocSignatureSpan">xhr.</span>put (uri, options, callback)](#apidoc.element.xhr.put)



# <a name="apidoc.module.xhr"></a>[module xhr](#apidoc.module.xhr)

#### <a name="apidoc.element.xhr.XMLHttpRequest"></a>[function <span class="apidocSignatureSpan">xhr.</span>XMLHttpRequest ()](#apidoc.element.xhr.XMLHttpRequest)
- description and source-code
```javascript
function noop() {}
```
- example usage
```shell
...
var window = require("global/window")
var isFunction = require("is-function")
var parseHeaders = require("parse-headers")
var xtend = require("xtend")

module.exports = createXHR
createXHR.XMLHttpRequest = window.XMLHttpRequest || noop
createXHR.XDomainRequest = "withCredentials" in (new createXHR.XMLHttpRequest()) ? createXHR.XMLHttpRequest : window.XDomainRequest

forEachArray(["get", "put", "post", "patch", "head", "delete"], function(method) {
createXHR[method === "delete" ? "del" : method] = function(uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
...
```

#### <a name="apidoc.element.xhr.del"></a>[function <span class="apidocSignatureSpan">xhr.</span>del (uri, options, callback)](#apidoc.element.xhr.del)
- description and source-code
```javascript
del = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
...
  console.log(resp.body)
})
'''

or

'''js
xhr.del('/delete-me', { headers: { my: 'auth' } }, function (err, resp) {
  console.log(resp.statusCode);
})
'''

## Options

### 'options.method'
...
```

#### <a name="apidoc.element.xhr.get"></a>[function <span class="apidocSignatureSpan">xhr.</span>get (uri, options, callback)](#apidoc.element.xhr.get)
- description and source-code
```javascript
get = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xhr.head"></a>[function <span class="apidocSignatureSpan">xhr.</span>head (uri, options, callback)](#apidoc.element.xhr.head)
- description and source-code
```javascript
head = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xhr.patch"></a>[function <span class="apidocSignatureSpan">xhr.</span>patch (uri, options, callback)](#apidoc.element.xhr.patch)
- description and source-code
```javascript
patch = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xhr.post"></a>[function <span class="apidocSignatureSpan">xhr.</span>post (uri, options, callback)](#apidoc.element.xhr.post)
- description and source-code
```javascript
post = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
...

The 'xhr' module has convience functions attached that will make requests with the given method.
Each function is named after its method, with the exception of 'DELETE' which is called 'xhr.del' for compatibility.

The method shorthands may be combined with the url-first form of 'xhr' for succinct and descriptive requests. For example,

'''js
xhr.post('/post-to-me', function(err, resp) {
  console.log(resp.body)
})
'''

or

'''js
...
```

#### <a name="apidoc.element.xhr.put"></a>[function <span class="apidocSignatureSpan">xhr.</span>put (uri, options, callback)](#apidoc.element.xhr.put)
- description and source-code
```javascript
put = function (uri, options, callback) {
    options = initParams(uri, options, callback)
    options.method = method.toUpperCase()
    return _createXHR(options)
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
