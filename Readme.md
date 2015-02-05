[![NPM version][npm-img]][npm-url]
[![Build status][travis-img]][travis-url]
[![Test coverage][coveralls-img]][coveralls-url]
[![License][license-img]][license-url]
[![Dependency status][david-img]][david-url]

### efetch

extend the `window.fetch`,
the polyfill for [fetch spec](https://fetch.spec.whatwg.org/)
is [github/fetch](https://github.com/github/fetch).

### polyfills

* [window.fetch](https://github.com/github/fetch)

```sh
$ bower install fetch

# or

$ npm install github/fetch
```

* [es6 promise](https://github.com/components/es6-promise)

```sh
$ bower install es6-promise
```

### document

* set() - set http header
* send() - send data,
* query() - set query string
* append() - append form data

```js
efetch.get(url, options)
.query({
  type: 1
})
.query({
  name: 'hello'
})
.then(function(res) {
  // fetch response
})
.catch(function(err) {
  // ...
});

// send json

efetch.post(url, options)
.send({
  type: 1
})
.send({
  name: 'hello'
})
.then(function(res) {
  // fetch response
})
.catch(function(err) {
  // ...
});

// send urlencoded

efetch.post(url, options)
.send('type=1')
.send('name=hello')
.then(function(res) {
  // fetch response
})
.catch(function(err) {
  // ...
});

// set header

efetch.post(url, options)
.set({
  'content-type': 'application/json'
})
.send({
  type: 1
})
.send({
  name: 'hello'
})
.then(function(res) {
  // fetch response
})
.catch(function(err) {
  // ...
});

// send form (upload file)

efetch.post(url, options)
.append({
  filename: 'user.png'
})
.append({
  file: document.querySelector('input[type="file"]')files[0]
})
.then(function(res) {
  // fetch response
})
.catch(function(err) {
  // ...
});
```

### License
MIT

[npm-img]: https://img.shields.io/npm/v/efetch.svg?style=flat-square
[npm-url]: https://npmjs.org/package/efetch
[travis-img]: https://img.shields.io/travis/coderhaoxin/efetch.svg?style=flat-square
[travis-url]: https://travis-ci.org/coderhaoxin/efetch
[coveralls-img]: https://img.shields.io/coveralls/coderhaoxin/efetch.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/coderhaoxin/efetch?branch=master
[license-img]: http://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[license-url]: http://opensource.org/licenses/MIT
[david-img]: https://img.shields.io/david/coderhaoxin/efetch.svg?style=flat-square
[david-url]: https://david-dm.org/coderhaoxin/efetch
