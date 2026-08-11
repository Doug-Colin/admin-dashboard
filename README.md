# Dashboard Layout

## About

An Odin Project exercise on web development fundamentals; copying a layout, primarily using grid.

# Key Lessons

## Best Practices

### Avoid letting html semantics dictate the location of class attributes intended for layout:

- If you let the semantic structure of the html dictate which elements have class attributes for layout, laying out the page will be unintuitive and unnecessarily complicated.

- This is because Grid and flexbox containers impart their respective behaviors on _direct children_ only.

- Writing semantic html means determining which element is appropriate by the meaning or significance of its content within the page. For example, a consider a semantically appropriate `<nav>` element: It could contain a `<ul>`, which contains multiple `<li>`s, each containing an `<a>` element, which wraps an `<img>` icon and a text `<span>` as siblings.

- Now, in order to lay out those list item anchor links, where should we place the layout class attributes? They belong wherever it is easiest to maintain a _direct child_ relationship between the element serving as the parent layout container, and the repeated elements that represent the layout container's items. In this case, it's probably best to put the parent layout container class on the `<nav>`, and the child layout classes on the `<li>`.

- However, there are situations where the html structure makes this less obvious, and in those cases, there's no need to alter it! It's better to simply create the direct parent-child relationship wherever you want by using wrapper elements like `<div>` or `<section>`. These have no semantic meaning and are intended for exactly this use.

- TLDR: No one really loves a div soup, but there's a reason it's so common.

## How To:

### Truncate Text Content to Multiple Lines with Ellipsis

Eventually, the property `line-clamp` will let us easily truncate text content with an ellipse, to however many lines we want. As of August 2026 however, there's insufficiently broad browser support for recommended use (MDN).

For now, set ellipsis shortening of text after multiple lines by setting the following properties on any text node that you want to truncate:

- set `display: -webkit-box;`
- `-webkit-box-orient: vertical;`
- `-webkit-line-clamp: 3;`
- `overflow: hidden;`
- These `webkit-` prefixed properties are deprecated, but continuously supported ['Note: For legacy support' (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/line-clamp)
