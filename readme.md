# Coding Guidelines

# Structure

Stylesheet files are imported in a specific order, following the [ITCSS][2] principal.

The layers are:

1. Settings: variables, breakpoints, grid settings and other configuration
2. Tools: preprocessor mixins and functions or vendor tools like compass, bourbon, susy etc.
3. Generic: resets, nomralize etc.
4. Base: unclassed elements
5. Objects: design patterns like grids and other layout scaffolds without visual styling
6. Components: reusable chunk of UI
7. Helper: single helper or global state classes to overwrite or extend element styles, often using !important


# Naming conventions

## File names

Every partial needs to be assigned to one of the layers and has to live in the corresponding folder with the layers name.

```
▾ settings
  _global.scss
  _breakpoints.scss
▾ tools
  _functions.scss
  _mixins.scss
▾ generic
  _reset.scss
▾ base
  _typography.scss
  _hyperlinks.scss
▾ objects
  _grid.scss
▾ components
  _button.scss
  _progress-bar.scss
  _masthead.scss
▾ helper
  _responsive.scss
  _spacing.scss
  _layout.scss
```

## Class names

Class names follow an [extended BEM naming convention][3]. Classes are prefixed to indicate which layer they belong to. Breakpoints are added as a suffix with an @. State classes are prefixes with `is-` or `has-` and can be global like `is-hidden` or tied to the scope of a component as an additional class `.c-collapsible-list-item.is-collapsed`.

`o-object-name`, `o-object-name__element-name`, `o-object-name--modifier`  
`c-component-name`, `c-component-name__element-name`, `c-component-name--modifier`  
`h-helper-name`, `h-helper-name-size`, `is-hidden@tablets-up`

## Breakpoints

Helper classes that should only apply to certain breakpoints or breakpoint ranges are suffixed like this:

`…@dektops` = Apply to desktops only  
`…@tablets-down` = Apply to tablets and smaller  
`…@notebooks-up` = Apply to notebooks and larger

## Sizes

Sizes are always written in short form like this:

As a modifier to an object or component: `o-grid--s`, `c-avatar--xl`  
Or as part of a single helper class name: `h-tp-m`

Usually you will have the following range of sizes: `xs, s, m, l, xl, xxl` while `m` is usually the default size.


## Orientation

The following abbreviations should be used to indicate orientation:

`t` = top as in `h-tm-s` (add small margin at top of element)  
`r` = right  
`b` = bottom  
`l` = left  
`h` = horizontal (left and right)  
`v` = vertical (top and bottom)

A missing orientation indicator means usually that the CSS should target all sides (top, right, bottom and left). For example: `h-m-l` adds a large margin on all sides.

# Further reading

* [Less CSS mess][1]


[1]: http://thomasbyttebier.be/blog/less-css-mess "Less CSS mess"
[2]: https://www.youtube.com/watch?v=1OKZOV-iLj4&hd=1 "Managing CSS with ITCSS (Video)"
[3]: http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/ "BEMIT Taking the BEM Naming Convention a Step Further"
