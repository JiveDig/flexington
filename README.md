# Flexbox Grid
## A grid framework using flexbox. Allows column width declaration from the wrapping element.
* Allows for nesting of columns.
* [View FlexGrid codepen](http://codepen.io/JiveDig/pen/bEvwdp).

## Requirements
`.col` must be an immediate child of `.row`, this allows for nested grids

## How To Use
1. Add the wrapping class `.row`
Example: `<div class="row">`.
1. Add a class of `.col` to each immediate child element that is part of the column grid.
1. Add classes (for breakpoints xs, sm, md, lg) to a container element to declare the total columns out of the 12.
Example: `<div class="col col-xs-12 col-sm-6 col-md-4">`.

## Notes
`.row` uses negative margins when dealing with gutters. Try not to add styling to the `.row` itself, instead stying a different wrapping element to avoid potential problems from the negative margin.