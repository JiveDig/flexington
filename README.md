# Flexington

## A grid framework using flexbox. Originally forked from [FlexBox Grid](http://flexboxgrid.com/).
* Optional gutters between grid items (not in FlexBox Grid)
* Declare various breakpoints right in your HTML.
* Breakpoints: xs < 544px, sm > 544px, md > 768px, lg > 992px, xl > 1200px
* Easily nest columns.
* Support for WordPress Galleries (not in FlexBox Grid)
* [View Flexington codepen](http://codepen.io/JiveDig/pen/vXmykK).

## Requirements
`.col` must be an immediate child of `.row`, this allows for nested grids

## How To Use
### Notes
`.row` uses negative margins when dealing with gutters. Try not to add styling to the `.row` itself, instead stying a different wrapping element to avoid potential problems from the negative margin.

### Raw HTML
1. Add the wrapping class `.row`
Example: `<div class="row">`.
1. Add a class of `.col` to each immediate child element that is part of the column grid.
1. Add classes (for breakpoints xs, sm, md, lg) to a container element to declare the total columns out of the 12.
Example: `<div class="col col-xs-12 col-sm-6 col-md-4 col-lg-3 col-xl-2">`.

### Genesis Archives
```
// Flexington archive wrap opening html
add_action( 'genesis_before_loop', 'prefix_do_flexington_wrap_open', 100 );
function prefix_do_flexington_wrap_open() {
	echo '<div class="row gutter-30">';
}

// Flexington archive wrap closing html
// If archive pagination throws things off, try hooking into `genesis_after_endwhile`
add_action( 'genesis_after_loop', 'prefix_do_flexington_wrap_close', 0 );
function prefix_do_flexington_wrap_close() {
	echo '</div>';
}

// Add Flexington col classes to .entry
add_filter( 'genesis_attr_entry', 'prefix_flexington_archive_wrap' );
function prefix_flexington_archive_wrap( $attributes ) {
	$attributes['class'] = $attributes['class']. ' col col-xs-12 col-sm-6 col-md-4 col-lg-3 col-xl-2';
	return $attributes;
}
```

## WordPress Galleries
Flexington 2.1.0+ includes support for WordPress Galleries (1, 2, 3, 4, 6 columns only)
* Remove default WordPress gallery CSS
```
// Turn off gallery CSS
add_filter( 'use_default_gallery_style', '__return_false' );
```
* Bonus: Remove unsupported options from the gallery dropdown
```
/**
 * Add custom CSS to <head>
 *
 * @return void
 */
add_action( 'admin_head', 'prefix_remove_unsupported_flexington_gallery_options' );
function prefix_remove_unsupported_flexington_gallery_options() {
    echo '<style type="text/css">
        .gallery-settings .columns option[value="5"],
        .gallery-settings .columns option[value="7"],
        .gallery-settings .columns option[value="8"],
        .gallery-settings .columns option[value="9"] {
            display:none !important;
            visibility: hidden !important;
        }
        </style>';
}
```
