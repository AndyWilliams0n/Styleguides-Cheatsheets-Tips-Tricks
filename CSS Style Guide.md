# CSS

What is CSS? Cascading Style Sheets is a style sheet language used for describing the look and formatting of a document written in a markup language.

* CSS files use the extension .css.



## Guidelines

One of the simplest forms of a styleguide is a set of rules regarding syntax and formatting. Having a standard way of writing (literally writing) CSS means that code will always look and feel familiar to all members of the team.

Further, code that looks clean feels clean. It is a much nicer environment to work in, and prompts other team members to maintain the standard of cleanliness that they found. Ugly code sets a bad precedent.



## CSS Syntax

Please checkout my [CSS Reference Guide](CSS%20Reference%20Guide.md) for more information.



## Coding Style

### Spacing

* Use soft-tabs with a four space indent.
* Put spaces after : in property declarations.
* Put spaces before { in rule declarations.
* Put line breaks between rulesets.
* When grouping selectors, keep individual selectors to a single line. Indent code where applicable.
* Place closing braces of declaration blocks on a new line.
* Each declaration should appear on its own line for more accurate error reporting.
* End all declarations with a semi-colon. The last declaration's is optional, but your code is more error prone without it.

### Formatting

* Use hex color codes #000 unless using rgba().
* Uppercase all hex values, use #FFF as it makes it nicer to look at.
* Use shorthand hex values where available, use #FFF instead of #FFFFFF.
* Avoid specifying units for zero values, use margin: 0; instead of margin: 0px;.
* Don't prefix property values or color parameters with a leading zero (e.g., .5 instead of 0.5)
* Strive to limit use of shorthand declarations to instances where you must explicitly set all the available values.
* Use hyphenated class names (no camelCase or snake_case).

### Examples

Here are some good examples that apply the above guidelines:

Example:

    /* Example of good basic formatting practices */

    .class {
        property: value;
        property: value;
    }

    /* Example of individual selectors getting their own lines (for error reporting) */

    .class,
    .class,
    .class {
        property: value;
        property: value;
    }

    /* Avoid unnecessary shorthand declarations */

    .not-so-good {
        margin: 0 0 20px;
    }

    .good {
        margin-bottom: 20px;
    }



## Single Declarations

In instances where a rule set includes only one declaration, consider removing line breaks for readability and faster editing. Any rule set with multiple declarations should be split to separate lines.

Example:

    /* Single declarations on one line (Optional) */

    .span1 { property: value; }



## Declaration Order

Related property declarations should be grouped together following the order:

1. Positioning
2. Box model
3. Typographic
4. Visual
5. Other

Example:

    .declaration-order {

    /* Positioning */
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 100;

    /* Box-model */
        display: block;
        float: right;
        width: 100px;
        height: 100px;

    /* Typography */
        font: normal 13px "Helvetica Neue", sans-serif;
        line-height: 1.5;
        color: #333;
        text-align: center;

    /* Visual */
        background-color: #FFF;
        border: 1px solid #E0E0E0;
        border-radius: 3px;

    /* Other */
        opacity: 1;

    }



## Pixels vs. Ems

* Use px for font-size, because it offers absolute control over text.
* Additionally, line-height is preferred because it does not inherit a percentage value of its parent element, but instead is based on a multiplier of the font-size.



## Naming Conventions

Always use spinal-case when naming classes. It makes it easier to read when viewing lots of code.

Example:

    /* Good */

    .this-is-using-spinal-case { ... }

    /* Not so good */

    .thisIsUsingCamelCase { ... }



## CSS Specificity Guidelines

If you must use an id selector (#selector) make sure that you have no more than one in your rule declaration.

** It's best to remove classes all together, this will make it easier to code for as ID's take priority over classes. **

Example:

    /* Not so good */

    #header .search #quicksearch { ... }



The class names disabled, mousedown, danger, hover, selected, and active should always be namespaced by a class (button.selected is a good example).

### Examples

Here is a good and bad example that apply the above guidelines:

Example:

    /* Not so good */

    <div id="container" class="card">
        <h1 id="header"></h1>
        <p></p>
    </div>
    .card { background: #FFF; }
    #container h1#header { color: #777; }
    h1 : hover { color: #C00!important; }

    /* Good */

    <div class="card">
        <h1></h1>
        <p></p>
    </div>

    .card { background: #FFF; }

    .card h1 { color: #777; }

    .card h1:hover { color: #C00; }



## Duplication Of Code

Try not to duplicate code. If you have 4 buttons that you need to code up, don't create 4 classes and style each one:

Example:

    /* Not so good */

    <a class="button-one">Button 1</a>
    <a class="button-two">Button 2</a>
    <a class="button-three">Button 3</a>
    <a class="button-four">Button 4</a>

    .button-one {
        background: #EEE;
        color: red;
    }
    .button-two {
        background: #EEE;
        color: green;
    }
    .button-three {
        background: #EEE;
        color: blue;
    }
    .button-four {
        background: #EEE;
        color: black;
    }

instead, try to break up those styles to more reusable and cleaner CSS:

Example:

    /* Good */

    <a class="button red">Button 1</a>
    <a class="button green">Button 2</a>
    <a class="button blue">Button 3</a>
    <a class="button black">Button 4</a>

    .button { background: #EEE; }

    .button.red { color: red; }

    .button.green { color: green; }

    .button.blue { color: blue; }

    .button.black { color: black; }



## Media Query Placement

Place media queries as close to their relevant rule sets whenever possible.



## Prefixed Properties

Don't prefix your CSS, use Gulp Autoprefixer (Preprocessing), Compass Autoprefixer (Preprocessing), [Prefix Free](http://leaverou.github.io/prefixfree/) or any other prefixer that you prefer. That way your code will remain clean and easy to read.



By 4ndywilliamson
version 0.1
