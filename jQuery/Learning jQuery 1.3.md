# Learning jQuery 1.3

> The jQuery library provides a general-purpose abstraction layer for common web scripting.

- Access elements in a document
- Modify the appearance of a web page
- Alter the content of a document
- Respond to a user's interaction
- Animate changes being made to a document (visual feedback)
- AJAX
- Simplify common JavaScript tasks (iteration and array manipulation)

### jQuery 1.3 (January 2009) 
- A major overhaul of the selector engine (Sizzle) provided a huge boost to the library's performance
- Event delegation became formally supported

### Loading jQuery (with a local version as a fallback)
- Inspired from (https://html5boilerplate.com/)
``` html
<script src="//code.jquery.com/jquery-1.3.2.min.js"></script>
<script>window.jQuery || document.write('<script src="js/vendor/jquery-1.3.2.min.js"><\/script>')</script>

```

## Selectors

- CSS selectors
- jQuery's own custom selectors
- jQuery's DOM traversal methods

> The DOM is a family-tree structure of sorts (parents, children, etc...). 
The resulting set of elements from selectors and methods is always wrapped in a jQuery object. 
jQuery objects are different from regular DOM elements or node lists (do not provide the same methods and properties for some tasks).

### tag name, id, and class
`$('p)` - selects all paragraphs in the document   
`$('#some-id')` - selects the single element in the document which has an id of _"some-id"_   
`$('.some-class')` - selects all elements in the document that have a class of _"some-class"_   


