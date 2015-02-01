#SCSS

Welcome to my SCSS Style guide.

##Coding style

###Spacing

###Formatting

* Use // for comment blocks (instead of /* */). (SCSS only)



##File organization

In general, the SCSS file organization should follow something like this:

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
    ├── responsive
    │   └── _responsive.scss
    ├── pages
    │   ├── _home.scss
    │   └── _aboutus.scss
    └── scss.scss



##Bundle up your SCSS

Including (S)CSS files
This will be in the scss.scss file in the root 

    @import "globals/reset",
        "globals/variables",
        "globals/scaffolding",
        "components/header"...



##Specificity (classes vs. ids)

Elements that occur exactly once inside a page should use IDs, otherwise, use classes. When in doubt, use a class name.

* **Good** candidates for ids: header, footer, modal popups.
* **Bad** candidates for ids: navigation, item listings, item view pages (ex: issue view).

When styling a component, start with an element + class namespace (prefer class names over ids), prefer direct descendant selectors by default, and use as little specificity as possible. Here is a good example:

    <ul class="category-list">
        <li class="item">Category 1</li>
        <li class="item">Category 2</li>
        <li class="item">Category 3</li>
    </ul>

    .category-list { // element + class namespace
        
        // Direct descendant selector > for list items
        
        > li { list-style-type: disc; }
        
        // Minimal specificity for all links
        
        a { color: #f00; }
    }

    

##Nesting in Sass

Avoid unnecessary nesting. Just because you can nest, doesn't mean you always should. Consider nesting only if you must scope styles to a parent and if there are multiple elements to be nested.

    // Without nesting
    
    .table > thead > tr > th { }
    .table > thead > tr > td { }
    
    // With nesting
    
    .table {
        > thead {
            > tr {
                > th { }
                > td { }
            }
        }        
    }



By 4ndywilliamson
Version 0.1