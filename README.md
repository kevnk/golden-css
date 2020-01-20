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

