# SASS & SCSS

What is SASS? Sass is a CSS pre-processor with syntax advancements. Style sheets in the advanced syntax are processed by the program, and turned into regular CSS style sheets. However, they do not extend the CSS standard itself.

Sass has two syntaxes. The new main syntax (as of Sass 3) is known as “SCSS” (for “Sassy CSS”), and is a superset of CSS3’s syntax. This means that every valid CSS3 stylesheet is valid SCSS as well.

* SCSS files use the extension .scss.



## Guidelines

One of the simplest forms of a styleguide is a set of rules regarding syntax and formatting. Having a standard way of writing (literally writing) SCSS means that code will always look and feel familiar to all members of the team.

Further, code that looks clean feels clean. It is a much nicer environment to work in, and prompts other team members to maintain the standard of cleanliness that they found. Ugly code sets a bad precedent.



## SCSS Syntax

Please checkout my [SCSS Reference Guide](SCSS%20Reference%20Guide.md) for more information.



## Coding style

### Spacing

* Use soft-tabs with a four space indent.
* Put spaces after : in property declarations.
* Put spaces before { in rule declarations.
* Put line breaks between rulesets.
* Put line breaks between nested rulesets.
* When grouping selectors, keep individual selectors to a single line. Indent code where applicable.
* Place closing braces of declaration blocks on a new line.
* Each declaration should appear on its own line for more accurate error reporting.
* End all declarations with a semi-colon. The last declaration's is optional, but your code is more error prone without it.

### Formatting

* Use hex color codes #000 unless using rgba(), include colours only in the _variables.scss.
* Uppercase all hex values, use #FFF as it makes it nicer to look at.
* Use shorthand hex values where available, use #FFF instead of #FFFFFF.
* Avoid specifying units for zero values, use margin: 0; instead of margin: 0px;.
* Don't prefix property values or color parameters with a leading zero (e.g., .5 instead of 0.5)
* Strive to limit use of shorthand declarations to instances where you must explicitly set all the available values.
* Use // for comment blocks.
* Use hyphenated class names (no camelCase or snake_case).

### Examples

Here is a good examples that applies the above guidelines:

Example:

    // Example of good basic formatting practices

    .class {

        property: value;

        &.class {
            property: value;
        }

        .child-class {
            property: value;
        }

    }



## File organization

In general, the SCSS file organization should follow something like this:

Example:

    scss styles
    ├── components
    │   ├── _buttons.scss
    │   └── _footer.scss
    │   └── _header.scss
    │   └── _input.scss
    ├── global
    │   ├── _global.scss
    │   ├── _reset.scss
    │   ├── _scafolding.scss
    │   └── _variables.scss
    ├── pages
    │   ├── _home.scss
    │   └── _aboutus.scss
    └── scss.scss

Keep the size of files to a comfortable length, ensuring they are easy to navigate.

Having situations where you either have files too long or so small that means you have so many, makes it harder to find the selectors you want.

Partials are: _partial.scss and are a common naming convention.



## Bundle up your SCSS

Including (S)CSS files
This will be in the scss.scss file in the root

Example:

    @import "globals/reset",
        "globals/variables",
        "globals/scaffolding",
        "components/header"...



## Bundle ordering

* List vendor/resets first.
* List global variables/mixins next.
* List global dependancies next.
* List author dependancies next.
* List patterns next.
* List page specific next.
* List components last.



## SCSS ordering

* List @extend(s) first.
* List standard property/values next.
* List @include(s) next.
* List additional classes next.
* List child selectors Last.

Example:

    .class {

        @extends %module;

        property: $colour;

        @include transition(all);

        &.class {
            property: value;
        }

        > p {
            property: value;
            @include transition(all);
        }

    }



## Nesting in Sass

Avoid unnecessary nesting. Just because you can nest, doesn't mean you always should. Consider nesting only if you must scope styles to a parent and if there are multiple elements to be nested.

Example:

    // Maximum recomended nesting, 4 levels

    table {

        tr {

            th {
                property: value;
            }

            td {

                property: value;

                &:hover {
                    property: value;
                }

            }

        }

    }

Try to keep any 4th level nested CSS for interactions only.

Example:

    .show, .hide, :hover, :active



## Media query placement

Place media queries as close to their relevant rule sets whenever possible. A good idea is to include them at the base of each scss file so they are easy to find and maintain.



## Media query bubbling

If you add a @media query by nesting it inside a selector, Sass will "bubble" that @media query and the new rule outside of the nest and back out to the root of your style sheet.

The will mean that your CSS is more readable and much easier to maintain.

Example:

    @mixin device($media) {
        @if $media == mobile {
            @media only screen and (max-width: 320px) { @content; }
        }
        @else if $media == screen {
            @media only screen and (min-width: 321px) and (max-width: 1024px) { @content; }
        }
        @else if $media == wide-screen {
            @media only screen and (min-width: 1024px) { @content; }
        }
    }

    .class {
        property: 200px;
        @include device(mobile) { property: 100% ;}
        @include device(screen) { property: 200px; }
        @include device(wide-screen) { property: 500px; }
    }

    // Output becomes:

    .class { property: 200px; }

    @media only screen and (max-width: 320px) {
        .class { property: 100%; }
    }
    @media only screen and (min-width: 321px) and (max-width: 1024px) {
        .class { property: 200px; }
    }
    @media only screen and (min-width: 1024px) {
        .class { property: 500px; }
    }



## Variable names

Variables in Sass are a powerful way to define values in one place that can be reused in multiple places in your project. Choosing good names can be difficult!

* Use semantic variable names.
* Use useful naming conventions

Example:

    // Not so good

    $black: #000111;

    // Good: (Naming conventions: element - property - value)

    $html-background-colour: #000111;





## Tips and helpers

* Compile your SCSS to CSS with Source Maps, makes debugging easier in Chrome.
* Live websites should only ever have compiled CSS.
* Don't commit .css files to your repo, GIT or SVN.
* Comment your code.
* Use variables for all colours and numbers.



By 4ndywilliamson
Version 0.1
