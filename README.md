# ThumboJS - a NodeJS Thumbor Url Builder

ES2015-style Thumbor URL generator for Node JS.

> browsers are not supported simply because to use the code in the browser would imply either having to supply the encryption-key to the browser or not use an encryption key, neither of which is a good idea.

a refactor of the following projects (with thanks to them!) ...
 - https://github.com/dcaramelo/ThumborUrlBuilder
 - https://github.com/rafaelcaricio/ThumborJS

## Install <em>(requires [npm](https://docs.npmjs.com/getting-started/what-is-npm))</em>

```sh
npm install thumbor
```

## Testing

You can run a basic set of tests (and linting) with:
```
npm test
```

You can run tests to validate the hash generation with:
```
npm run test-hashing
```
> N.B. these require Python & Thumbor be [installed locally](http://thumbor.readthedocs.io/en/latest/installing.html)


You can run tests against a running instance of Thumbor with:
```
npm run test-requests
```
> N.B. by default the requests will be performed against "**http://localhost:8888**", you can change this by setting the env-var `THUMBOR_URL`


## Usage

```javascript
const ThumborJS = require('thumbor');

// Your encryption key may be NULL, but if so your links will be unsafe (this is definitely NOT RECOMMENDED).
const myKey     = 'MY_KEY'; 

// init url generator
const tugen     = new ThumborJS('http://localhost:8888', myKey);

// generate a url
const url       = tugen.setImagePath('foobar.png').resize(50,50).buildUrl();
```
