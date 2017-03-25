# api documentation for  [compression (v1.6.2)](https://github.com/expressjs/compression#readme)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-compression.svg)](https://travis-ci.org/npmdoc/node-npmdoc-compression)
#### Node.js compression middleware

[![NPM](https://nodei.co/npm/compression.png?downloads=true)](https://www.npmjs.com/package/compression)

[![apidoc](https://npmdoc.github.io/node-npmdoc-compression/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-compression_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-compression/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-compression/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/expressjs/compression/issues"
    },
    "contributors": [
        {
            "name": "Douglas Christopher Wilson",
            "email": "doug@somethingdoug.com"
        },
        {
            "name": "Jonathan Ong",
            "email": "me@jongleberry.com",
            "url": "http://jongleberry.com"
        }
    ],
    "dependencies": {
        "accepts": "~1.3.3",
        "bytes": "2.3.0",
        "compressible": "~2.0.8",
        "debug": "~2.2.0",
        "on-headers": "~1.0.1",
        "vary": "~1.1.0"
    },
    "description": "Node.js compression middleware",
    "devDependencies": {
        "eslint": "2.9.0",
        "eslint-config-standard": "5.3.1",
        "eslint-plugin-promise": "1.1.0",
        "eslint-plugin-standard": "1.3.2",
        "istanbul": "0.4.3",
        "mocha": "2.4.5",
        "supertest": "1.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "cceb121ecc9d09c52d7ad0c3350ea93ddd402bc3",
        "tarball": "https://registry.npmjs.org/compression/-/compression-1.6.2.tgz"
    },
    "engines": {
        "node": ">= 0.8.0"
    },
    "files": [
        "LICENSE",
        "HISTORY.md",
        "index.js"
    ],
    "gitHead": "b9c63ced82b9f719cd5d9fd250c8432b00752d89",
    "homepage": "https://github.com/expressjs/compression#readme",
    "license": "MIT",
    "maintainers": [
        {
            "name": "dougwilson",
            "email": "doug@somethingdoug.com"
        }
    ],
    "name": "compression",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/expressjs/compression.git"
    },
    "scripts": {
        "lint": "eslint **/*.js",
        "test": "mocha --check-leaks --reporter spec --bail",
        "test-cov": "istanbul cover node_modules/mocha/bin/_mocha -- --check-leaks --reporter dot",
        "test-travis": "istanbul cover node_modules/mocha/bin/_mocha --report lcovonly -- --check-leaks --reporter spec"
    },
    "version": "1.6.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module compression](#apidoc.module.compression)
1.  [function <span class="apidocSignatureSpan">compression.</span>filter (req, res)](#apidoc.element.compression.filter)



# <a name="apidoc.module.compression"></a>[module compression](#apidoc.module.compression)

#### <a name="apidoc.element.compression.filter"></a>[function <span class="apidocSignatureSpan">compression.</span>filter (req, res)](#apidoc.element.compression.filter)
- description and source-code
```javascript
function shouldCompress(req, res) {
  var type = res.getHeader('Content-Type')

  if (type === undefined || !compressible(type)) {
    debug('%s not compressible', type)
    return false
  }

  return true
}
```
- example usage
```shell
...
function shouldCompress(req, res) {
  if (req.headers['x-no-compression']) {
    // don't compress responses with this request header
    return false
  }

  // fallback to standard filter function
  return compression.filter(req, res)
}
'''

### res.flush

This module adds a 'res.flush()' method to force the partially-compressed
response to be flushed to the client.
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
