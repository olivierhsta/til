# Bundle JavaScript assets with gulp.js and webpack

I use this config files to bundle ES6 JavaScript code into browser friendly code.

## dependencies
First of all, we need to install all the necessary dependencies.
```
npm install --save-dev gulp gulp-babel@next @babel/core @babel/preset-env webpack-stream
```

## webpack.config.js
First we have to set up webpack to bundle our modules.
```javascript
const path = require('path');

module.exports = {
    entry: {
      page1: './js/page1/page1.js',
      page2: './js/page2/page2.js'
    },

    output: {
      path: path.join(__dirname, 'components'),
      filename: '[name].js',
    }
};
```

This takes every JavaScript files list in the `entry` array and bundles all their modules into one file which will be named after the `entry` index.  This methods allows for multiple entries and multiple outputs, which may or may not be useful for a given usecase.

For example. if `./js/page1/page1.js` imports one module `modulePage1.js` and `./js/page1/page2.js` imports one module `modulePage2.js`, the webpack output will be two files, namely `page1.js` and `page2.js` (whereas the default webpack config will only give one file).

## .babelrc
The babel config file needs to specify the presets.
```javascript
{
  "presets": ["@babel/preset-env"]
}
```
## gulpfile.js
Next, we tell gulp to first pipe our code through webpack (using the `webpack.config.js` file we just created).

Then, we take the outputed files and pipe them through babel, which compiles our ES6 syntax into traditional JavaScript syntax.

Then, the files get uglify.

Finally, we specify the output folder to be `./build/js/`.
```javascript
'use strict';

const gulp = require('gulp');
const babel = require("gulp-babel");
const webpack = require('webpack-stream');
const uglify = require('gulp-uglify');

gulp.task("js:bundle", function () {
  return gulp.src(['./js/**/*.js', '!gulpfile.js'])
    .pipe(webpack(require('./webpack.config.js')))
    .pipe(babel())
    .pipe(uglify())
    .pipe(gulp.dest("./build/js"));
});
```

The final output for the previous example will be `./build/js/page1.js` and `./build/js/page2.js`.
