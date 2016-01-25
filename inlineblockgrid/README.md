# Inline Block Grid
A grid based on the examples I first learned from MixIsUp.js
<br />https://mixitup.kunkalabs.com/learn/tutorial/responsive-grids/

## Known Issue
When HTML doesn't have a space or line break between elements, `.text-align: justify;` doesn't work.
<br />[See this CSS-tricks discussion.](https://css-tricks.com/fighting-the-space-between-inline-block-elements/)

## How to use
* Add a class of `.row` to the container element.
* Add responsive classes for the breakpoints you want to utilize
* Example `<div class="col-xs-12 col-sm-6 col-md-4">`
