# helper-copyright [![NPM version](https://badge.fury.io/js/helper-copyright.svg)](http://badge.fury.io/js/helper-copyright)

> Template helper for adding a basic, one-line copyright statement, with formatting appropriate for LICENSE/LICENSE-MIT or README templates. Used with Verb, but should work with any Handlebars, Lo-Dash, underscore, or any template engine that allows helper functions to be registered.

## Install with [npm](npmjs.org)

```bash
npm i helper-copyright --save
```

## Example

Add a copyright statement, with author and year(s) in effect (verb templates):

```js
{%= copyright() %}
//=> Copyright (c) 2014 Jon Schlinkert

{%= copyright({year: 2012}) %}
//=> Copyright (c) 2012-2014 Jon Schlinkert

{%= copyright({year: 2012, linkify: true}) %}
//=> Copyright (c) 2014 [Jon Schlinkert](https://github.com/jonschlinkert)
```

## Usage

> This should work with any engine, here are a few examples

Given the following locals:

```js
var locals = {author: {name: 'Jon Schlinkert', url: 'https://github.com/jonschlinkert'}};
```

### [Lo-Dash](https://github.com/jonschlinkert/template)

As a helper:

```js
_.template('<%= copyright({author: author}) %>', locals, {
  imports: {'copyright': require('helper-copyright')}
});
//=> Copyright (c) 2014 Jon Schlinkert
```

As a mixin:

```js
_.mixin({'copyright': require('helper-copyright')});
_.template('<%= copyright({author: author}) %>', locals);
//=> Copyright (c) 2014 Jon Schlinkert
```

### [template](https://github.com/jonschlinkert/template)

```js
template.helper('copyright', require('helper-copyright'));
template.render('<%= copyright() %>', function(err, content) {
  console.log(content);
  //=> Copyright (c) 2014 Jon Schlinkert'
});
```

### [assemble](https://github.com/assemble/assemble)

```js
assemble.helper('copyright', require('helper-copyright'));
assemble.render('{{copyright this}}', function(err, content) {
  console.log(content);
  //=> Copyright (c) 2014 Jon Schlinkert'
});
```

### [verb](https://github.com/jonschlinkert/verb)

```js
verb.helper('copyright', require('helper-copyright'));
verb.render('{%= copyright() %}', function(err, content) {
  console.log(content);
  //=> Copyright (c) 2014 Jon Schlinkert'
});
```

### [handlebars](https://github.com/wycats/handlebars.js/)

```js
var handlebars = require('handlebars');
handlebars.registerHelper('copyright', require('helper-copyright'));
handlebars.compile('{{copyright this}}')(locals);
//=> Copyright (c) 2014 Jon Schlinkert
```

## Related projects

* [helper-license](https://github.com/helpers/helper-license): Template helper for dynamically generating a basic, one-line license statement… [more](https://github.com/helpers/helper-license)
* [helper-reflinks](https://github.com/helpers/helper-reflinks): Template helper for generating a list of markdown formatted reference… [more](https://github.com/helpers/helper-reflinks)
* [helper-related](https://github.com/helpers/helper-related): Template helper for generating a list of links to the… [more](https://github.com/helpers/helper-related)
* [verb](https://github.com/assemble/verb): Documentation generator for GitHub projects. Extremely powerful, easy to use,… [more](https://github.com/assemble/verb)

## Running tests

Install dev dependencies:

```bash
npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/helpers/helper-copyright/issues)

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright (c) 2014-2015 Jon Schlinkert
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on April 25, 2015._

<!-- reflinks generated by verb-reflinks plugin -->

[verb]: https://github.com/assemble/verb
[template]: https://github.com/jonschlinkert/template
[assemble]: http://assemble.io