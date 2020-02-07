# Golden CSS
### A golden-ratio preset for Bootstrap styles

[![npm version](https://badge.fury.io/js/golden-css.svg)](https://badge.fury.io/js/golden-css)

## How to use

### Install
`yarn add golden-css -D` or `npm install golden-css --dev`

### Import
__app.scss__
```
@import '~golden-css/scss/base';
@import '~golden-css/scss/golden';
```

#### Or, for more versatility:

__app.scss__
```
@import 'base';
@import '~golden-css/scss/golden';
```

___base.scss__
```
@import 'variables'; // or whatever functions/mixins you may have
@import '~golden-css/scss/base';
```

Now, you can use _base.scss to have access to all variables in a scoped component without class definitions being repeated.

### Debug help
The seemingly random css values (e.g. `padding: 2.42705rem`) can be hard to debug. With some small configuration, you can change it to show a much more friendly`padding: var(--spacer-5)`.

To set this up, you'll need to inject an `$environment` variable from webpack. 

__NOTE: Use the CSS calc function when doing any arithmetic so it work for css variables AND sass variables. e.g. `calc(#{$spacer-1} * 2)`__

#### For Laravel Mix
Update your sass line in webpack.mix.js to this:

```
mix.sass('resources/sass/app.scss', 'public/css', {
        data: `$environment: '${process.env.NODE_ENV}';`,
    })
```

#### For VueCLI
Add this to your vue.config.js 

```
module.exports = {
    // ...
    
    css: {
        loaderOptions: {
            sass: {
                prependData: `$environment: '${process.env.NODE_ENV}';`,
            },
        },
    },

    // ...
}
```
