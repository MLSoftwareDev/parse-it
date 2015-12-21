# parse-it [![Support this project][donate-now]][paypal-donations]

Configurable string templating, without separators.

## Installation

```sh
$ npm i --save parse-it
```

## Example

```js
const parseIt = require("parse-it");

// Replace strings
console.log(parseIt("Hello WORLD!", { WORLD: "Mars" }));
// => Hello Mars!

// Use functions
console.log(parseIt("Random number: random", { random: () => Math.random() }));
// => Random number: 0.21168493130244315

// Using as class
var Parser = parseIt.Parser;

// Display a date
var p = new Parser({
    d: function (d) { return d.getDate() }
  , M: function (d) { return d.getMonth() }
  , YYYY: function (d) { return d.getFullYear() }
});

console.log(p.run("d/M/YYYY", [new Date(1989, 11, 20)]));
// => 20/11/1989
```

## Documentation

### `ParseIt(obj)`
The `ParseIt` class. It can be used to use the same data object but with different formats/arguments.

#### Params
- **Object** `obj`: An object containing the fields to replace.

### `parseIt(format, args)`
run
Replaces the fields in the format string with data coming from the data object.

#### Params
- **String** `format`: The format input.
- **Array** `args`: An array of arguments to be passed to the replace function (stored in the `obj` object).

#### Return
- **String** The result as string.

### `parseIt(format, obj, args)`
A wrapper around the `ParseIt` class. The `ParseIt` constructor is accessible using `parseIt.Parser`.

#### Params
- **String** `format`: The format input.
- **Object** `obj`: An object containing the fields to replace.
- **Array** `args`: An array of arguments to be passed to the replace function (stored in the `obj` object).

#### Return
- **String** The result as string.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

## License

[MIT][license] © [Ionică Bizău][website]

[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(http%3A%2F%2Fionicabizau.net)&year=2015#license-mit
[website]: http://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md