# SASS & SCSS Reference Guide

## SCSS Syntax

### Variables:

Variables are a way to store information that you want to reuse throughout your stylesheet.

Example:

    $variable: value;

    .class {
        property: $variable;
    }



### Nesting:

Sass will let you nest your CSS selectors.

Example: Simple Nesting

    .class {
        .class2 {
            property: value;
        }
    }

    // Output becomes:

    .class .class2 { property: value; }



Example: Nesting Same Level Elements

    .class {

        property: value;

        &.class2 {
            property: value;
        }

        &-extension {
            property: value;
        }

    }

    // Output becomes:

    .class { property: value; }

    .class.class2 { property: value; }

    .class-extension { property: value; }



Example: Media Query Nesting

    .class {

        width: 100%;

        @media screen and (max-width:940px) {
            width: auto;
        }

    }

    // Output becomes:

    .class { width: 100%; }

    @media screen and (max-width:940px) {
        .class { width: auto; }
    }



### Partials:

You can create partial Sass files that contain little snippets of CSS that you can include in other Sass files. A partial is simply a Sass file named with a leading underscore: _partial.scss. The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file. Sass partials are used with the @import directive.



### Import:

Sass will take the file that you want to import and combine it with the file you're importing into so you can serve a single CSS file to the web browser.

Example:

    @import 'reset';

    body { ... }



### Mixins:

A mixin lets you make groups of CSS declarations that you want to reuse throughout your site. You can even pass in values to make your mixin more flexible.

Example:

    @mixin border-radius($radius) {
        border-radius: $radius;
    }

    .class {
        @include border-radius(10px);
    }

    // Output becomes:

    .class { border-radius: 10px; }



### Extend & Inheritance

Using @extend lets you share a set of CSS properties from one selector to another.

*It helps keep your SCSS very DRY*

Example:

    .class {
        property: value;
        property: value;
        property: value;
    }

    .class2 {
        @extend .class;
        property: value;
    }

    // Output becomes:

    .class,
    .class2 {
        property: value;
        property: value;
        property: value;
    }

    .class2 { property: value; }



### Placeholders

They are very similar to class selectors, but instead of using a "." at the start, the percent character "%" is used. Placeholder selectors will not show up in the compiled CSS, only the selectors that extend them will be included.

Example:

    %module {
        property: value;
        property: value;
        property: value;
    }

    .class {
        @extend %module;
        property: value;
    }

    // Output becomes:

    .class {
        property: value;
        property: value;
        property: value;
        property: value;
    }




### Operators

Sass has a handful of standard math operators like +, -, *, /, and %.

Example:

    .class {
        property: 60px / 960px * 100%;
    }

    // Output becomes:

    .class { property: 6.25%; }



### @if, @for, @each & @while

Sass control directives are useful for creating libraries for reuse and distribution.

Example: @if

    $boolean: true !default;

    @mixin display($boolean) {

        @if $boolean {
            property: block
        }
        @else {
            property: none
        }

    }

    .class {
        @include display($boolean);
    }

    // Output becomes:

    .class { property: block; }



Example: @for

    $class: class !default

    @for $index from 1 through 4 {

        .#{$class}-#{$index} {
            property: 0px + $index
        }

    }

    // Output becomes:

    .class-1 { property: 1px; }

    .class-2 { property: 2px; }

    .class-3 { property: 3px; }

    .class-4 { property: 4px; }



Example: @each

    $array: success error warning;

    @each $item in $array {

        .class-#{$item} {
            property: url(#{$icon}.png);
        }

    }

    // Output becomes:

    .class-success { property: url(success.png); }

    .class-error { property: url(error.png); }

    .class-warning { property: url(warning.png); }



Example: @while

    $count: 4;

    @while $count > 0 {

        .class-#{$count} {
            property: 10px * $count;
        }

        $count: $count - 2;

    }

    // Output becomes:

    .class-4 { property: 40px; }

    .class-2 { property: 20px; }




### Functions

Functions can perform tasks based on the data it receives during compile time.

In the example below, the lightness() function is a built-in Sass function that returns the lightness of a color's RGB value between 0 and 100.

This function will return an opposite text colour based on the background colour.

Example:

    $notification-light: #DDD;
    $notification-dark: #222

    @function set-text-color($colour) {
        @if (lightness( $colour ) > 50) {
          @return #000000;
        }
        @else {
          @return #FFFFFF;
        }
    }

    .notification-light {
        background: $notification-light;
        color: set-text-color($notification-light);
    }

    .notification-dark {
        background: $notification-dark;
        color: set-text-color($notification-dark);
    }



## Typography

| Includes | Values |
| -------- | ------ |
| @include font-size-small | 12 |
| @include font-size-regular | 16 |
| @include font-size-large | 24 |
| @include font-size-x-large | 32 |
| @include font-size-xx-large | 48 |
| @include font-size-xxx-large | 64 |
| @include font-size-xxxx-large | 96 |
|  |  |
| $font-weight-light | 300 |
| $font-weight-regular | 400 |
| $font-weight-bold | 600 |
|  |  |
| $font-family-text | 'Helvetica Neue', Helvetica, Arial, sans-serif |
| $font-family-display | Georgia, 'Times New Roman', Times, serif |
| $font-family-code | Consolas, 'Lucida Console', Courier, monospace |



## Resolution Breakpoints

| Includes | Values |
| -------- | ------ |
| $mobile-small | 240 |
| $mobile-large | 320 |
| $tablet-small | 480 |
| $tablet-large | 768 |
| $screen-small | 1024 |
| $screen-large | 1280 |
| $screen-x-large | 1920 |
| $screen-xx-large | 2400 |



By 4ndywilliamson
Version 0.1
