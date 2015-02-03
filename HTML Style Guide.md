# HTML

What is HTML? Hypertext Markup Language is a standardized system for tagging text files to achieve font, colour, graphic, and hyperlink effects on World Wide Web pages.

* HTML files use the extension .html.



## Guidelines

One of the simplest forms of a styleguide is a set of rules regarding syntax and formatting. Having a standard way of writing (literally writing) HTML means that code will always look and feel familiar to all members of the team.

Further, code that looks clean feels clean. It is a much nicer environment to work in, and prompts other team members to maintain the standard of cleanliness that they found. Ugly code sets a bad precedent.



## Coding Style

### Spacing

* Use soft tabs with a four space indent - they're the only way to guarantee code renders the same in any environment.
* Nested elements should be indented once.
* Always use double quotes, never single quotes, on attributes.
* Don't include a trailing slash in self-closing elements—the HTML5 spec says they're optional.
* Don’t omit optional closing tags (e.g. < /li > or < /body >).

Example:

    <!DOCTYPE html>
    <html>
        <head>
            <title>Page title</title>
        </head>
        <body>
            <img src="images/company-logo.png" alt="logo">
            <h1>Hello, world!</h1>
        </body>
    </html>



### HTML5 Doctype

Enforce standards mode and more consistent rendering in every browser possible with this simple doctype at the beginning of every HTML page.

Example:

    <!DOCTYPE html>
    <html>
        <head>
        </head>
    </html>



### Language Attribute

From the HTML5 spec:

* Authors are encouraged to specify a lang attribute on the root html element, giving the document's language. This aids speech synthesis tools to determine what pronunciations to use, translation tools to determine what rules to use, and so forth.

Example:

    <html lang="en-gb">
        <!-- ... -->
    </html>



### IE Compatibility Mode

Internet Explorer supports the use of a document compatibility <meta> tag to specify what version of IE the page should be rendered as. Unless circumstances require otherwise, it's most useful to instruct IE to use the latest supported mode with edge mode.

Example:

    <meta http-equiv="X-UA-Compatible" content="IE=Edge">



### Character Encoding

Quickly and easily ensure proper rendering of your content by declaring an explicit character encoding. When doing so, you may avoid using character entities in your HTML, provided their encoding matches that of the document (generally UTF-8).

Example:

    <meta charset="UTF-8">



### Practicality Over Purity

Strive to maintain HTML standards and semantics, but not at the expense of practicality. Use the least amount of markup with the fewest intricacies whenever possible.



### Attribute Order

HTML attributes should come in this particular order for easier reading of code.

* class
* id, name
* data-
* src, for, type, href, value
* title, alt
* role

Classes make for great reusable components, so they come first. Ids are more specific and should be used sparingly (e.g., for in-page bookmarks), so they come second.

Example:

    <a class="" id="" data-bind="" href="#"> link </a>

    <input class="" type="text">

    <img src="" alt="">



### Reducing Markup

Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML. Take the following example:

Example:

    // Not so good

    <span class="class">
        <img src="">
    </span>

    // Good

    <img class="class" src="">



By 4ndywilliamson
Version 0.1
