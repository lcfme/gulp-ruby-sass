# gulp-ruby-sass [![Build Status](https://travis-ci.org/sindresorhus/gulp-ruby-sass.svg?branch=master)](https://travis-ci.org/sindresorhus/gulp-ruby-sass)

> Compile Sass to CSS with [Ruby Sass](http://sass-lang.com/install)

This is slower than [gulp-sass](https://github.com/dlmanning/gulp-sass), but more stable and feature-rich.

*Issues with the output should be reported on the Sass [issue tracker](https://github.com/nex3/sass/issues).*


## Install

```sh
$ npm install --save-dev gulp-ruby-sass
```

You also need to have [Ruby](http://www.ruby-lang.org/en/downloads/) and [Sass](http://sass-lang.com/download.html) installed. If you're on OS X or Linux you probably already have Ruby; test with `ruby -v` in your terminal. When you've confirmed you have Ruby, run `gem install sass` to install Sass.


## Usage

```js
var gulp = require('gulp');
var sass = require('gulp-ruby-sass');

gulp.task('default', function () {
	return gulp.src('src/app.scss')
		.pipe(sass({sourcemap: true}))
		.pipe(gulp.dest('dist'));
});
```


## API

### sass(options)

#### options


##### sourcemap

Type: `Boolean`  
Default: `false`

Enable Source Map.

**Requires Sass 3.3.0**


##### trace

Type: `Boolean`  
Default: `false`

Show a full traceback on error.


##### unixNewlines

Type: `Boolean`  
Default: `false` on Windows, otherwise `true`

Use Unix-style newlines in written files.


##### check

Type: `Boolean`  
Default: `false`

Just check syntax, don't evaluate.


##### style

Type: `String`  
Default: `nested`

Output style. Can be `nested`, `compact`, `compressed`, `expanded`.


##### precision

Type: `Number`  
Default: `3`

How many digits of precision to use when outputting decimal numbers.


##### quiet

Type: `Boolean`  
Default: `false`

Silence warnings and status messages during compilation.


##### compass

Type: `Boolean`  
Default: `false`

Make Compass imports available and load project configuration (`config.rb` located close to the `gulpfile.js`).


##### debugInfo

Type: `Boolean`  
Default: `false`

Emit output that can be used by the FireSass Firebug plugin.


##### lineNumbers

Type: `Boolean`  
Default: `false`

Emit comments in the generated CSS indicating the corresponding source line.


##### loadPath

Type: `String|Array`

Add one or more Sass import paths.


##### require

Type: `String|Array`

Require one or more Ruby libraries before running Sass.


##### cacheLocation

Type: `String`  
Default: `.sass-cache`

The path to put cached Sass files.


##### noCache

Type: `Boolean`  
Default: `false`

Don't cache to sassc files.


##### bundleExec

Type: `Boolean`  
Default: `false`

Run `sass` with [bundle exec](http://gembundler.com/man/bundle-exec.1.html): `bundle exec sass`. For bundler to work correctly you must add the Gemfile and Gemfile.lock to your `gulp.src()` glob.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
