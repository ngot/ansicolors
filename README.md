#ansicolors 
###modified from [ansistyles](https://github.com/thlorenz/ansicolors).

Functions that surround a string with ansicolor codes so it prints in color.

In case you need styles, like `bold`, have a look at [ansistyles](https://github.com/ngot/ansicolors.git).


```js
var colors = require('ansicolors');

// foreground colors
var redHerring = colors.red('herring');
var blueMoon = colors.blue('moon');
var brighBlueMoon = colors.brightBlue('moon');

console.log(redHerring);      // this will print 'herring' in red
console.log(blueMoon);        // this 'moon' in blue
console.log(brightBlueMoon);  // I think you got the idea

// background colors
console.log(colors.bgYellow('printed on yellow background'));
console.log(colors.bgBrightBlue('printed on bright blue background'));

// mixing background and foreground colors
// below two lines have same result (order in which bg and fg are combined doesn't matter)
console.log(colors.bgYellow(colors.blue('printed on yellow background in blue')));
console.log(colors.blue(colors.bgYellow('printed on yellow background in blue')));
```

## Advanced API

**ansicolors** allows you to access opening and closing escape sequences separately.

```js
var colors = require('ansicolors');

function inspect(obj, depth) {
  return require('utiljs').inspect(obj, false, depth || 5, true);
}

console.log('open blue', inspect(colors.open.blue));
console.log('close bgBlack', inspect(colors.close.bgBlack));

// => open blue '\u001b[34m'
//    close bgBlack '\u001b[49m'
```

## Tests

Look at the [tests](https://github.com/ngot/ansicolors/blob/master/test/ansicolors.js) to see more examples and/or run them via: 

    js test/ansicolors.js

## Alternatives

**ansicolors** tries to meet simple use cases with a very simple API. However, if you need a more powerful ansi formatting tool, 
