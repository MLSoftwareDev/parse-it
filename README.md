
# parse-it

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Version](https://img.shields.io/npm/v/parse-it.svg)](https://www.npmjs.com/package/parse-it) [![Downloads](https://img.shields.io/npm/dt/parse-it.svg)](https://www.npmjs.com/package/parse-it)

> Configurable string templating, without separators.

## :cloud: Installation

```sh
$ npm i --save parse-it
```


## :clipboard: Example



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

## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help from me, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:


## :memo: Documentation


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



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`formatoid`](https://github.com/IonicaBizau/formatoid#readme)—Tiny and fast module for formatting date objects.

## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2015#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
