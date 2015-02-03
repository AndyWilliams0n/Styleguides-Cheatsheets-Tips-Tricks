# CSS Reference Guide

## CSS Syntax

### Selectors:

Example:

    Element - h1, h2, h3, p, a, div...
    Class - .something
    ID - #something



### Declarations

Example:

    { color: #FFFFF; }
        |       |
     Property Value



## CSS1 Selector Syntax

| Pattern | Description |
| ------- | ----------- |
| X | Element, class or ID |
|  |  |
| X:link | A hyperlink anchor, not yet visited |
| X:visited | A hyperlink anchor, visited |
| X:hover | A hyperlink anchor, on mouse hover |
| X:active | A hyperlink anchor, on click |
|  |  |
| X::first-line | First formatted line |
| X::first-letter | First formatted letter |
|  |  |
| X.class | Element whose class is "class" |
| X#id | Element with ID equal to "id" |

## CSS2 Selector Syntax

| Pattern | Description |
| ------- | ----------- |
| X | Element, class or ID |
|  |  |
| *    | Any element |
| X[foo] | With a "foo" attribute |
| X[foo="bar"] | Whose "foo" attribute value is exactly equal to "bar" |
| X[foo~="bar"] | Whose "foo" attribute value is a list of whitespace-separated values, one of which is exactly equal to "bar" |
| X[foo="en"] | Whose "foo" attribute has a hyphen-separated list of values beginning (from the left) with "en" |
|  |  |
| X:first-child | First child of its parent |
| X:lang(en) | Language "en" (document language specifies "en") |
|  |  |
| X::before | Before X content |
| X::after | After X content |
|  |  |
| X > Y | Y is a child of X |
| X + Y | Y immediately preceded by X |

## CSS3 Selector Syntax

| Pattern | Description |
| ------- | ----------- |
| :root | Root of the document, usually HTML |
|  |  |
| X[foo^="bar"] | Whose "foo" attribute value begins exactly with the string "bar" |
| X[foo$="bar"] | Whose "foo" attribute value ends exactly with the string "bar" |
| X[foo*="bar"] | Whose "foo" attribute value contains the substring "bar" |
|  |  |
| X:nth-child(n) | The n-th child of its parent, n = number |
| X:nth-last-child(n) | The n-th child of its parent, counting from the last one, n = number |
| X:nth-of-type(n) | The n-th sibling of its type, n = number |
| X:nth-last-of-type(n) | The n-th sibling of its type, counting from the last one, n = number |
|  |  |
| X:last-child | Last child of its parent |
| X:first-of-type | First sibling of its type |
| X:last-of-type | Last sibling of its type |
| X:only-child | Only child of its parent |
| X:only-of-type | Only sibling of its type |
|  |  |
| X:empty | Has no children (including text nodes) |
| X:target | Being the target of the referring URI |
| X:enabled | A user interface element which is enabled |
| X:disabled | A user interface element which is disabled |
| X:checked | A user interface element which is checked |
| X:not(Y) | Element does not match simple selector Y |
|  |  |
| X ~ Y |  Y preceded by an E element |



By 4ndywilliamson
version 0.1
