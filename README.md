# Code patterns

This is our HTML, CSS and JavaScript style guide. This guide contains feelings, thoughts and code from another's very good style guides. In [our company](http://shareprime.com.br), you have to keep this principles for your coding. It will maitain a great quality in our code, and it will be easy to another people complements your code.

## General definitions

### Protocols
Omit the protocol portion (http:, https:) from URLs pointing to images and other media files, style sheets, and scripts unless the respective files are not available over both protocols. Omitting the protocol—which makes the URL relative—prevents mixed content issues and results in minor file size savings.

```
<!-- Not recommended -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```
```
<!-- Recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

### Indentation

Use 1 tab at a time. Don't mix tabs and spaces for indentation.

### Capitalization

Use only lowercase. Always.

###Trailing Whitespace

Remove trailing white spaces. Trailing white spaces are unnecessary and can complicate diffs.

```
<!-- Not recommended -->
<p>What?  </p>
<!-- Recommended -->
<p>Yes please.<p>
```

### General Meta Rules

#### Encoding

Use UTF-8 (no BOM).

### Comments

Explain code as needed, where possible. Use comments to explain code: What does it cover, what purpose does it serve, why is respective solution used or preferred? (This item is optional as it is not deemed a realistic expectation to always demand fully documented code. Mileage may vary heavily for HTML and CSS code and depends on the project’s complexity.)

### TO-DO

Mark todos and action items with TODO. Highlight todos by using the keyword TODO only, not other common formats like @@. Append a contact (username or mailing list) in parentheses as with the format TODO(contact). Append action items after a colon as in TODO: action item.

```
{# TODO(john.doe): revisit centering #}
<center>Test</center>
```
```
<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```

## HTML Coding Style

### Document Type

Use HTML5. Only HTML5. HTML5 (HTML syntax) is preferred for all HTML documents: ```<!DOCTYPE html>```.

### HTML Validity

Use valid HTML where possible. Use valid HTML code unless that is not possible due to otherwise unattainable performance goals regarding file size. Use tools such as the [W3C HTML](https://validator.w3.org/nu/) validator to test. Using valid HTML is a measurable baseline quality attribute that contributes to learning about technical requirements and constraints, and that ensures proper HTML usage.

### Semantics

Use HTML according to its purpose.Use elements (sometimes incorrectly called “tags”) for what they have been created for. For example, use heading elements for headings, p elements for paragraphs, a elements for anchors, etc. Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.

```
<!-- Not recommended -->
<div onclick="goToRecommendations();">All recommendations</div>
```
```
<!-- Recommended -->
<a href="recommendations/">All recommendations</a>
```





## CSS Coding Style

- Use a four space indent.
- Put spaces after : in property declarations.
- Spaces before braces: put spaces before { in rule declarations.
- Do not use trailing commas when listing multiple selectors
- Separate selector and property declarations with a new line
- Separate rules with a new line
- End properties declarations with a ;
- Alphabetize properties within rule declarations
- Properties with values of 0 should *not* have units
- Use lowercase hex color codes #fff unless using rgba.
- Use /* */ for block comments (instead of //).
- Use a maximum line length of 80 characters (rationale: looking at files side-by-side)
- Use dashes in selectors instead of underscores (.my-class, not .my_class)

Here is good example syntax:

```css
/* This is a good example! */
.styleguide-format,
.other-format,
.third-format {
    background: rgba(0,0,0,0.5);
    border: 1px solid #0f0;
    color: #000;
    margin: 0;
}

.next-rule {
    color: #000;
}
```

## CSS Specificity Guidelines

Elements that occur **exactly once** inside a page should use IDs, otherwise, use classes. When in doubt, use a class name.

- **Good** candidates for ids: header, footer, modal popups.
- **Bad** candidates for ids: navigation, item listings, item view pages (ex: issue view).

- If you must use an id selector (`#selector`) make sure that you have no more than one in your rule declaration. A rule like `#header .search #quicksearch { ... }` is considered harmful. Curious why? Check out this primer on [CSS specificity](http://css-tricks.com/specifics-on-css-specificity/).
- Do not combine id selectors with tags (`div#container`). The id should be specific enough, and should not be repeated elsewhere to necessitate the tag name. Try to follow the same guidelines for classes as well.
- When modifying an existing element for a specific use, try to use specific class names. Instead of `.listings-layout.bigger` use rules like `.listings-layout.listings-bigger`. Think about ack/greping your code in the future.
- Key (rightmost) Selectors should be as specific as possible. For example `a.navigation-link` instead of `#navigation-links a`. This has [performance implications](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/).

