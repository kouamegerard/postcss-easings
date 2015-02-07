# PostCSS Easings [![Build Status](https://travis-ci.org/postcss/postcss-easings.svg)](https://travis-ci.org/postcss/postcss-easings)

<img align="right" width="135" height="95" src="http://postcss.github.io/postcss/logo-leftp.png" title="Philosopher’s stone, logo of PostCSS">

[PostCSS] plugin to replace easing name from [easings.net] to `cubic-bezier()`
function.

```css
.snake {
    transition: all 600ms ease-in-sine;
}
.camel {
    transition: all 600ms easeInSine;
}
```

```css
.snake {
    transition: all 600ms cubic-bezier(0.47, 0, 0.745, 0.715);
}
.camel {
    transition: all 600ms cubic-bezier(0.47, 0, 0.745, 0.715);
}
```

[easings.net]: http://easings.net/
[PostCSS]:     https://github.com/postcss/postcss

## Usage

Without options:

```js
postcss([ require('postcss-easings') ])
```

With options:

```js
postcss([
    require('postcss-easings')({
      easings: { easeJump: 'cubic-bezier(.86,0,.69,1.57)' }
    })
])
```

See [PostCSS] docs for examples for your environment.

Also you can get all build-in easings:

```js
require('postcss-easings').easings;
```

## Options

### `easings`

Allow to set custom easigs:

```js
require('postcss-easings')({
  easings: { easeJump: 'cubic-bezier(.86,0,.69,1.57)' }
})
```

Plugin will convert custom easigs names between camelCase and snake-case.
So example below adds `easeJump` and `ease-jump` easings.

Custom easing name must start from `ease` and contain only letters and `-`.

You can create custom easing on [cubic-bezier.com].

[cubic-bezier.com]: [http://cubic-bezier.com/]
