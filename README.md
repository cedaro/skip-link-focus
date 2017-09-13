# Skip Link Focus

Make "skip to content" links more accessible.

## Usage

Include `skip-link-focus.js` above the closing `</body>` tag and initialize it:

```html
<script src="skip-link-focus.js"></script>
<script>skipLinkFocus.init();</script>
```

Or if you're using Browserify:

```js
require( 'skip-link-focus' ).init();
```

`init()` takes an optional `options` argument:
- `options.selector` {String} Specifies a DOM selector where skip links are to be found. This is used to handle an edge case where, if a hash is present in the URL on initial load (or refresh), clicking the skip link wouldn't actually fire a hashchange event, making the skip link unusable. Usage example: `init( { selector: '.generic-skip-link-class' } )`. Defaults to `.skip-link`.

## Background

Makes "skip to content" links work correctly in IE9, Chrome, and Opera to improve accessibility.

Initial code and background can be found here:  
http://www.nczonline.net/blog/2013/01/15/fixing-skip-to-content-links/

Further improvements were made in the [*_s* WordPress theme](https://github.com/Automattic/_s) by Automattic.

This module is based on the *_s* implementation with the following enhancements:

* Implemented the [UMD pattern](https://github.com/umdjs/umd) for use as an AMD, CommonJS, or stand-alone module.
* Added a skip link click handler to fix cases when a `hashchange` event isn't fired because the address bar already has the corresponding hash.
* Split the functionality into methods to provide a simple API.

Additional reading on skip link accessibility:
https://www.bignerdranch.com/blog/web-accessibility-skip-navigation-links/

## Testing

To manually test the script in a browser of your choice, run `npm test` and head to `http://localhost:5000/test/`.
