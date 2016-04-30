# Flexbox Grid
A grid framework using flexbox. Allows column width declaration from the wrapping element.
<br />Allows for nesting of columns.
<br />[View FlexGrid codepen](http://codepen.io/JiveDig/pen/bEvpBv).

## Requirements
`.col` must be an immediate child of `.flex-col-*`, this allows for nested grids

## Known bug/issue 
~~If last row doesn't have enough elements the elements in that row have a space between.
<br />See [this discussion](http://stackoverflow.com/questions/18744164/flex-box-align-last-row-to-grid).~~
This now works, thanks to [Keith Clark](http://keithclark.co.uk/articles/targeting-first-and-last-rows-in-css-grid-layouts/) for the great head start.

## How To Use
Add the class `.flex-cols` and classes (for breakpoints xs, sm, md, lg) to a container element to declare the total columns out of the 12.
<br />Example container: `<div class="flex-cols flex-col-xs-12 flex-col-sm-6 flex-col-md-4-8 flex-col-lg-3">`.
<br />Add a class of `.col` to each immediate child element that is part of the column grid.

## Modify
Search and replace percentage widths from [this grid column generator](http://thestizmedia.com/grid-column-generator/) if you want to change from defaults.
