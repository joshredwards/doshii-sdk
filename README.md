# Doshii Partner SDK [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url]
> A wrapper for the Doshii Partner API

Our API has been designed specifically to provide seamless integration into any POS, whether cloud or legacy. Built on the cloud, our SSL-secure API provides two-way communication between the POS and any app integrated with Doshii. Simply put, we're connecting hospitality.

Looking to integrate? Check us out at [Doshii.io](http://doshii.io) and one of our awesome staff will hook you up with an API key.

## Installation

```sh
$ npm install --save doshii-sdk
# or
$ yarn add doshii-sdk
```

## Usage

Your clientId and clientSecret will be picked up by default if they're set in your environment variables as 'DOSHII_CLIENT_ID' and 'DOSHII_CLIENT_SECRET', both or none must be set.

I would suggest only using the default 'v3' for version.  Specifying 'v2' will work for some of these methods, but reliability may be lacking.

```js
// Initialize the library
const Doshii = require('doshii-sdk')({
  clientId: 'YOUR_DOSHII_CLIENT_ID',
  clientSecret: 'YOUR_DOSHII_CLIENT_SECRET',
  env: 'sandbox',
  version: 'v3'
})

// The above settings would result in a base path of https://sandbox.doshii.co/partner/v3
```

Both promises and callbacks are supported by this library
```js
Doshii.Locations.retrieveAll()
  .then((result) => {
    // Do awesome stuff here
  }).catch((err) => {
    // Manage any errors here
  })

Doshii.Locations.findMenu({
  id: 'HASHED_LOCATION_ID'
}, (err, result) => {
  if (err) // Manage any errors here
  // Do awesome stuff here
})
```
A breakdown of the methods available are available on the [wiki](https://github.com/yjimk/doshii-sdk/wiki) page

##



## License

© MIT

Developed by [Jimmy Cann](mail@jimmycann.com) and maintained by the Doshii Team.


[npm-image]: https://badge.fury.io/js/doshii-sdk.svg
[npm-url]: https://npmjs.org/package/doshii-sdk
[travis-image]: https://travis-ci.org/yjimk/doshii-sdk.svg?branch=master
[travis-url]: https://travis-ci.org/yjimk/doshii-sdk
[daviddm-image]: https://david-dm.org/yjimk/doshii-sdk.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/yjimk/doshii-sdk
