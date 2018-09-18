# Encoding Guidelines for the Barnam Circus Broadsheet

## Divisions

Encode all divisions of the text with the  `<div>` element. Use the `@type` attribute to describe what you see as the classification of the division (e.g. advertisement, narrative, etc.). You get to choose what type of division to use!

### Example

```
<div type="advertisement">
<ab>Come to the Circus this Friday! Free peanuts!</ab>
</div>
```

## Paragraph-like content

Encode all paragraph-like content with the `<ab>` (anonymous block) element. We aren't going to use `<p>` (paragraph) element for this particular document

## Headings 

Encode all headings with the `<head>` element. **Note that this may be challenging for this document**, since there are a lot of stacked headings mixed with paragraph-like content. It's up to you to decide which segments are headings, and which are paragraph-like. Note that headings are always the first children of `<div>`. `<ab>` cannot come before `<head>` within a division.

### Example 

```
<div type="narrative">
<head>A Story</head>
<ab>Once upon a time...</ab>
</div>
```

## Unclear Text 

Encode unclear text with the `<unclear>` element. Provide a `@reason` for why the text is unclear. I'm not going to provide a list. You get to determine the reason you think the text is unclear!

### Example

```
<unclear reason="flawedReproduction">a</unclear>
```

## Dates

Encode dates with the `<date>` element. Provide a regularized version of the date with `@when` using the regularized `YYYY-MM-DD` format (or `YYYY` or `YYYY-MM`, if you only have the year or year and month, respectively).

### Example 

```
<date when="1999-02-27">February 27th, 1999</date>
<date when="1991-09-15">the 15th day of the 9th month in Anno Domine nineteen hundred and ninety one</date>
<date when="1800-04-13">Easter Day, 1800</date>
```

## Other features you may want to encode:

* Poems - use `<lg>` (line group)
* Poetic lines - use `<l>` (for line)

## Rendition

We will use the `@rend` attribute to encode most of the rendition for this document, using renditional ladders. Renditional ladders are ways of specifying information about the appearance and physical rendition of documents. The are encoded with the format of `keyword(argument)`. Rendition ladders can be stacked on top of each other, as in the following example:

```
<hi rend="case(allcaps)align(center)slant(italic)">Chapter I.</hi>
```

Keywords each have a specific set of arguments that they can take. The following is a list of keywords and their arguments:

* `align()` (for text alignment)
  * `center`
  * `left` (default)
  * `right` 
* `break()` (for whether the feature starts on a new line)
  * `yes`
  * `no`
* `case()` (i.e. upper-, lower-, etc.)
  * `allcaps`
  * `mixed` (default)
  * `smallcaps`
* `fill()` (fills everything between the current element and the next element with some character, line, etc.)
  * fills with the character placed in the parentheses (e.g. `fill(-)` would fill everything between two elements with dashes)
  * `#rule` (fills with a ruled line)
  * `#ornament` (fills everything with some ruled ornament)
* `indent()`
  * takes a number as its argument 
* `pre()`
  * same args as `fill()`
  * you may want to use `“` as argument for quotes
* `post()`
  * same args as `fill()`
  * you may want to use `"` for quotes
  * for notes, you could use `*` or superscripted numbers 
* `slant()` 
  * `italic`
  * `upright` (default)





