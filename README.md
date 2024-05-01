
# GenerationUX✨ Colorable App

Forked from [Colorable](https://github.com/jxnblk/colorable)

Take a set color palette and get contrast values for every possible combination – useful for finding safe color combinations with predefined colors and includes pass/fail scores for the WCAG accessibility guidelines.

Getting Started

npm i --save colorable
Usage

Pass an array of color strings or an object with color strings as values.

var colorable = require('colorable')

var colors = {
  red: 'red',
  green: 'green',
  blue: 'blue'
}

var result = colorable(colors, { compact: true, threshold: 0 })
Returns an array of colors with combinations for all other colors and their WCAG contrast values.

[
  {
    "hex": "#FF0000",
    "name": "red",
    "combinations": [
      {
        "hex": "#008000",
        "name": "green",
        "contrast": 1.28483997166146,
        "accessibility": {
          "aa": false,
          "aaLarge": false,
          "aaa": false,
          "aaaLarge": false
        }
      },
      {
        "hex": "#0000FF",
        "name": "blue",
        "contrast": 2.148936170212766,
        "accessibility": {
          "aa": false,
          "aaLarge": false,
          "aaa": false,
          "aaaLarge": false
        }
      }
    ]
  },
  ...
]
Accessibility object

Each key is a boolean value indicating if the color contrast meets the following criteria:

aa - greater than 4.5 (for normal sized text)
aaLarge - greater than 3 (for bold text or text larger than 24px)
aaa - greater than 7
aaaLarge - greater than 4.5
Options

compact

Type: Boolean (default: false)

If set to true, the result will be a smaller object that only includes hex value color strings, a name for each color (if an object is passed to the function), contrast, and accessibility values. When set to false, the result also includes the entire harthur/color object for each color, which includes other properties and methods for color manipulation.

threshold

Type: Number (default: 0)

When set, the colorable function only returns combinations that have a contrast above this value. This is useful for only seeing combinations that pass a minimum contrast level.

uniq

Type: Boolean (default: true)

When set to true, the array of colors is passed through lodash.uniq to remove duplicates.



MIT License

# colorable-app
