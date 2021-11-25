# Bukwild Stylus Library

Components:

- **index.styl** - The package.json `main`, this glob loads all mixins from the "lib" directory.  It also imports other stylus npm dependencies.  These dependencies are generally functions and mixins that have utility for all projects.
- **lib/** - Contains .styl files that define functions / imports. None of these files should contain any css selectors.  Read the comments within the individual files for details.
- **boilerplate.styl** - CSS rules that are intended to be loaded after a CSS reset or normalize on a project.  Essentially, this is a set of global Bukwild conventions.

## Settings

See [index.styl](index.styl) for some default vars.

## Recommendations

- Install https://github.com/WICG/focus-visible

## Examples

#### Fluid

`fluid()` uses media queries + viewport units to scale property values between an upward and lower limit as the viewport is resized.

```styl
.btn
  fluid padding, 20
```

Padding will be 20px when the viewport is 1440px wide (`fluid-default-max-break`) and 14px (`fluid-auto-min-size-factor`) when the viewport is 375px wide (`fluid-default-min-break`), linearly interpolated in between.

```styl
.btn
  fluid padding, 20, 10
```

Padding will be 20px when the viewport is 1440px wide and **10px** when the viewport is 375px wide, linearly interpolated in between.

```styl
.btn
  fluid(padding, 20, 10, min-break: 768px)
```

Padding will be 20px when the viewport is 1440px wide and 10px when the viewport is **768px** wide, linearly interpolated in between.


```styl
.btn
  fluid(padding, 20, 10, min-break: 768px, max-break: 1024px)
```

Padding will be 20px when the viewport is **1024px wide** and 10px when the viewport is 768px wide, linearly interpolated in between.


```styl
body
  fluid(--site-pad, 20, 10)
.btn
  padding calc(10px + var(--site-pad))
```

Use fluid to set a CSS custom variable that can be used inside of a `calc`.

