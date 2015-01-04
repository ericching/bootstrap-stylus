Meteor Bootstrap to Stylus 1.0.0
================================

This is a fork of the port of the amazing [Bootstrap 3.3.1](https://github.com/twbs/bootstrap) to [Stylus 0.47.0](http://learnboost.github.com/stylus/) to turn it into a Meteor package.

There might be some slight color differences due to the differences between the color functions in LESS and those in Stylus.

## Installing

```
meteor add innovae:bootstrap-stylus
```

To import whole bootstrap in your stylus file:
```stylus
@import '.meteor/local/build/programs/web.browser/packages/innovae_bootstrap-stylus/bootstrap'
```

Alternatively to import individual components:
```stylus
@import '.meteor/local/build/programs/web.browser/packages/innovae_bootstrap-stylus/bootstrap/alerts'
@import '.meteor/local/build/programs/web.browser/packages/innovae_bootstrap-stylus/bootstrap/variables'
@import '.meteor/local/build/programs/web.browser/packages/innovae_bootstrap-stylus/bootstrap/mixins'
```

## Compiling CSS from Stylus
Bootstrap Stylus uses [Grunt](http://gruntjs.com/) with convenient methods for working with the framework. To use it, install the required dependencies as directed and then run some Grunt commands.

### Install Grunt

From the command line:

1. Install `grunt-cli` globally with `npm install -g grunt-cli`.
2. Install the [necessary local dependencies](package.json) via `npm install`

When completed, you'll be able to run the various Grunt commands provided from the command line.

**Unfamiliar with `npm`? Don't have node installed?** That's a-okay. npm stands for [node packaged modules](http://npmjs.org/) and is a way to manage development dependencies through node.js. [Download and install node.js](http://nodejs.org/download/) before proceeding.

### Available Grunt commands

#### Compile CSS and JavaScript - `grunt dist`
`grunt dist` creates the `/dist` directory with compiled files. **Uses [UglifyJS](http://lisperator.net/uglifyjs/).**

#### Legacy 2.3.2 Theme - `grunt theme`
This will compile the `theme.styl` separately and output it to the `/dist` folder.

#### Watch - `grunt watch`
This is a convenience method for watching just Stylus files and automatically building them whenever you save.

### Troubleshooting dependencies

Should you encounter problems with installing dependencies or running Grunt commands, uninstall all previous dependency versions (global and local). Then, rerun `npm install`.

### Usage
* You may select what css components you want to include by editing `stylus/bootstrap.styl`.
* You may override [bootstrap variables](http://getbootstrap.com/customize/#less-variables) in your private code, for example
```
// myStyles.styl
$font-family-serif ?= 'Merriweather', serif
$font-family-base ?= $font-family-serif
@import "bower_components/bootstrap-stylus/stylus/bootstrap.styl" // Or wherever your bootstrap.styl is located
```
this allows flexibility for easily updating to new bootstrap versions. See [?=](https://learnboost.github.io/stylus/docs/operators.html#conditional-assignment--).
* You may select what javascript components you want by editing the uglify task in `gulpfile.js`. You can ommit components by removing them from the `uglify:dist:files` list.

## Original Authors

**Mark Otto**

+ [http://twitter.com/mdo](http://twitter.com/mdo)
+ [http://github.com/mdo](http://github.com/mdo)

**Jacob Thornton**

+ [http://twitter.com/fat](http://twitter.com/fat)
+ [http://github.com/fat](http://github.com/fat)

## This Author

**Eric Ching**

+ [https://twitter.com/innovaeinc](https://twitter.com/innovaeinc)
+ [https://github.com/ericching](https://github.com/ericching)

## Copyright and license

Copyright 2013 Twitter, Inc under [the Apache 2.0 license](LICENSE).
