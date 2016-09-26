# Code patterns

This is our HTML, CSS and JavaScript style guide. This guide contains feelings, thoughts and code from another's very good style guides. You have to keep this principles for your coding. It will maintain a great quality in our code, and it will be easy to another people complements your code. The most important thing, it's this guide is a live one. It means that if you have some sugestion, you can explain and edit this guide to make better and better. We know the environment between projects and developers and we think this possibility shall work better for everyone.

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

### Multimedia Fallback

For multimedia, such as images, videos, animated objects via canvas, make sure to offer alternative access. For images that means use of meaningful alternative text (alt) and for video and audio transcripts and captions, if available. Providing alternative contents is important for accessibility reasons: A blind user has few cues to tell what an image is about without @alt, and other users may have no way of understanding what video or audio contents are about either. (For images whose alt attributes would introduce redundancy, and for images whose purpose is purely decorative which you cannot immediately use CSS for, use no alternative text, as in alt="".)

```
<!-- Not recommended -->
<img src="spreadsheet.png">
```
```
<!-- Recommended -->
<img src="spreadsheet.png" alt="Spreadsheet screenshot.">
```

### Entity References

Do not use entity references. There is no need to use entity references like &mdash;, &rdquo;, or &#x263a;, assuming the same encoding (UTF-8) is used for files and editors as well as among teams. The only exceptions apply to characters with special meaning in HTML (like < and &) as well as control or “invisible” characters (like no-break spaces). This pattern is not valid only in e-mail marketing coding.

```
<!-- Not recommended -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.
```
```
<!-- Recommended -->
The currency symbol for the Euro is “€”.
```

### type Attributes

Omit type attributes for style sheets and scripts. Do not use type attributes for style sheets (unless not using CSS) and scripts (unless not using JavaScript). Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults. This can be safely done even for older browsers.

```
<!-- Not recommended -->
<link rel="stylesheet" href="//www.google.com/css/maia.css"
  type="text/css">
```
```
<!-- Recommended -->
<link rel="stylesheet" href="//www.google.com/css/maia.css">
```
```
<!-- Not recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"
  type="text/javascript"></script>
```
```
<!-- Recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

### General Formatting

Use a new line for every block, list, or table element, and indent every such child element.
Independent of the styling of an element (as CSS allows elements to assume a different role per display property), put every block, list, or table element on a new line.

Also, indent them if they are child elements of a block, list, or table element.

(If you run into issues around whitespace between list items it’s acceptable to put all li elements in one line. A linter is encouraged to throw a warning instead of an error.)

```
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
```
```
<ul>
	<li>Moe</li>
	<li>Larry</li>
	<li>Curly</li>
</ul>
```
```
<table>
	<thead>
    	<tr>
			<th scope="col">Income</th>
			<th scope="col">Taxes</th>
    	</tr>
  	</thead>
  	<tbody>
		<tr>
      		<td>$ 5.00</td>
      		<td>$ 4.50</td>
      	</tr>
    </tbody>
</table>
```

### HTML Quotation Marks

When quoting attributes values, use double quotation marks. Use double ("") rather than single quotation marks ('') around attribute values.

```
<!-- Not recommended -->
<a class='maia-button maia-button-secondary'>Sign in</a>
```
```
<!-- Recommended -->
<a class="maia-button maia-button-secondary">Sign in</a>
```

## CSS Coding Style

### General

- Use 1 tab at a time. Don't mix tabs and spaces for indentation.
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

### CSS Specificity Guidelines

Elements that occur **exactly once** inside a page should use IDs, otherwise, use classes. When in doubt, use a class name.

- **Good** candidates for ids: header, footer, modal popups.
- **Bad** candidates for ids: navigation, item listings, item view pages (ex: issue view).

- If you must use an id selector (`#selector`) make sure that you have no more than one in your rule declaration. A rule like `#header .search #quicksearch { ... }` is considered harmful. Curious why? Check out this primer on [CSS specificity](http://css-tricks.com/specifics-on-css-specificity/).
- Do not combine id selectors with tags (`div#container`). The id should be specific enough, and should not be repeated elsewhere to necessitate the tag name. Try to follow the same guidelines for classes as well.
- When modifying an existing element for a specific use, try to use specific class names. Instead of `.listings-layout.bigger` use rules like `.listings-layout.listings-bigger`. Think about ack/greping your code in the future.
- Key (rightmost) Selectors should be as specific as possible. For example `a.navigation-link` instead of `#navigation-links a`. This has [performance implications](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/).

### Use valid CSS where possible.

Unless dealing with CSS validator bugs or requiring proprietary syntax, use valid CSS code.

Use tools such as the [W3C CSS validator](https://jigsaw.w3.org/css-validator/) to test.

Using valid CSS is a measurable baseline quality attribute that allows to spot CSS code that may not have any effect and can be removed, and that ensures proper CSS usage.

### ID and Class Naming

Use meaningful or generic ID and class names.
Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.

Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.

Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as "helpers."

Using functional or generic names reduces the probability of unnecessary document or template changes.

```
/* Not recommended: meaningless */
#yee-1901 {}

/* Not recommended: presentational */
.button-green {}
.clear {}
```
```
/* Recommended: specific */
#gallery {}
#login {}
.video {}

/* Recommended: generic */
.aux {}
.alt {}
```

### ID and Class Name Style

Use ID and class names that are as short as possible but as long as necessary.
Try to convey what an ID or class is about while being as brief as possible.

Using ID and class names this way contributes to acceptable levels of understandability and code efficiency.

```
/* Not recommended */
#navigation {}
.atr {}
```
```
/* Recommended */
#nav {}
.author {}
```

### Type Selectors

Avoid qualifying ID and class names with type selectors.
Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.

Avoiding unnecessary ancestor selectors is useful for [performance reasons](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/).
```
/* Not recommended */
ul#example {}
div.error {}
```
```
/* Recommended */
#example {}
.error {}
```

### Shorthand Properties

Use shorthand properties where possible.
CSS offers a variety of [shorthand properties](https://www.w3.org/TR/CSS21/about.html#shorthand) (like font) that should be used whenever possible, even in cases where only one value is explicitly set.

Using shorthand properties is useful for code efficiency and understandability.

```
/* Not recommended */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```
```
/* Recommended */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

### 0 and Units

Omit unit specification after “0” values.
Do not use units after 0 values unless they are required.

```
margin: 0;
padding: 0;
```

### Prefixes

Prefix selectors with an application-specific prefix.
In large projects as well as for code that gets embedded in other projects or on external sites use prefixes (as namespaces) for ID and class names. Use short, unique identifiers followed by a dash.

Using namespaces helps preventing naming conflicts and can make maintenance easier, for example in search and replace operations.

```
.adw-help {} /* AdWords */
#maia-note {} /* Maia */
```

### ID and Class Name Delimiters

Separate words in ID and class names by a hyphen.
Do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.

```
/* Not recommended: does not separate the words “demo” and “image” */
.demoimage {}

/* Not recommended: uses underscore instead of hyphen */
.error_status {}
```
```
/* Recommended */
#video-id {}
.ads-sample {}
```

### CSS Formatting Rules

#### Declaration Order

Alphabetize declarations.
Put declarations in alphabetical order in order to achieve consistent code in a way that is easy to remember and maintain.

Ignore vendor-specific prefixes for sorting purposes. However, multiple vendor-specific prefixes for a certain CSS property should be kept sorted (e.g. -moz prefix comes before -webkit).

```
background: fuchsia;
border: 1px solid;
-moz-border-radius: 4px;
-webkit-border-radius: 4px;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em;
```

#### Block Content Indentation

Indent all [block content](https://www.w3.org/TR/CSS21/syndata.html#block), that is rules within rules as well as declarations, so to reflect hierarchy and improve understanding.

```
@media screen, projection {

  html {
    background: #fff;
    color: #444;
  }

}
```

#### Declaration Stops

Use a semicolon after every declaration.
End every declaration with a semicolon for consistency and extensibility reasons.

```
/* Not recommended */
.test {
  display: block;
  height: 100px
}
```
```
/* Recommended */
.test {
  display: block;
  height: 100px;
}
```

#### Declaration Block Separation

Use a space between the last selector and the declaration block.
Always use a single space between the last selector and the opening brace that begins the [declaration block](https://www.w3.org/TR/CSS21/syndata.html#rule-sets).

The opening brace should be on the same line as the last selector in a given rule.

```
/* Not recommended: missing space */
#video{
  margin-top: 1em;
}

/* Not recommended: unnecessary line break */
#video
{
  margin-top: 1em;
}
```
```
/* Recommended */
#video {
  margin-top: 1em;
}
```

#### Parting Words

Be consistent.

If you’re editing code, take a few minutes to look at the code around you and determine its style. If they use spaces around all their arithmetic operators, you should too. If their comments have little boxes of hash marks around them, make your comments have little boxes of hash marks around them too.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you’re saying rather than on how you’re saying it. We present global style rules here so people know the vocabulary, but local style is also important. If code you add to a file looks drastically different from the existing code around it, it throws readers out of their rhythm when they go to read it. Avoid this.