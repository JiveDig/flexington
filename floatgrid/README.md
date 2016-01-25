# Float Grid
A grid framework using floats. Allows column width declaration from the wrapping element.
<br />Allows for nesting of columns.
<br />[View FloatGrid codepen](http://codepen.io/JiveDig/pen/bEvpBv).

## Requirements
`.col` must be an immediate child of `.col-*`, this allows for nested grids

## How To Use
Add a class for **all** of the 4 breakpoints (xs, sm, md, lg) to a container element to declare the total columns out of the 12.<br />
Example container: `<div class="col-xs-12 col-sm-6 col-md-4 col-lg-3">`.<br />
Add a class of `.col` to each immediate child element that is part of the column grid.

## Modify
Search and replace percentage widths from [this grid column generator](http://thestizmedia.com/grid-column-generator/) if you want to change from defaults.
