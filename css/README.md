# CSS Coding Standards

The purpose of the 47 Degrees CSS Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing CSS to the same project. The end goal is unity, consistency, and the notion that a single entity created the outputted code.

This is a living document. The authors grow wiser with each passing day.

## Table of Contents

1. [General](#section-general)
2. [Comments](#section-comments)
3. [Format](#section-format)
4. [Selectors](#section-selectors)
5. [Properties](#section-properties)

<a name="section-general"></a>
## 1. General

* All code, regardless of who touches it, should look like a single person created it.
* All culprits who ignore the aforementioned rule will be docked one pint of beer.

<a name="section-comments"></a>
## 2. Comments

Well documented CSS is like a double rainbow; you just have to smile. We have all fallen victim to undocumented code from others; even being guilty of being too lazy to add our own comments to code. The mental statement "I'll add it later" is the precursor to "WTF, what is going on here". Let's avoid that.

To alleviate the ho-hum repetitive nature of entering properly formatted comments, configure your text editor (use your Editor Snippets or [TextExpander](http://smilesoftware.com/TextExpander/)).

* Use a Table of Contents (TOC) at the top of the document.
* Add a hashtag `#` to the opening section title e.g. `#Header`.
* Keep line-lengths short e.g. 50 columns.
* Comments are *good*. Go crazy with them.
* Use comments to break up CSS code logical sections

**Table of Contents:**

```css
/* Table of Contents
==================================================
	#Section-1
	#Section-2 */
```

**Section Comments:**
```css
/* #Section-1
================================================== */

.selector-1 {
	background: #fff;
	color: #333;
}

.selector-2 {
	background: #fff;
	color: #333;
}

/* #Section-2
================================================== */

.selector-3 {
	display: inline-block;
}

.selector-4 {
	background: #fff;
	color: #333;
}
```

<a name="section-format"></a>
## 3. Format

The first step to authoring consistent stylesheets begins with solid document structure and coding conventions.

* Indent each property with tabs, not spaces. Preference is tabs.
* One selector per line in multi-selector rulesets.
* Include a single space before the opening curly brace.
* Place the closing curly brace in the same column as the first character of the ruleset. 
* Include a single space after the colon of a declaration.
* Shorthand lowercase hex values (e.g. `#fff` not `#FFFFFF`).
* Use single or double quotes consistently. Preference is double quotes (e.g. `content: "";` not `content: ''`).
* Separate rulesets with *one* blank line.
* Separate sections with *two* blank lines (e.g. two blank lines after the last ruleset before entering a new section comment).

**Correct:**

```css
.selector-1,
.selector-2 {
	background: #fff;
	color: #333;
}
```

**Incorrect:**

```css
.selector-1, .selector-2 { background: #FFFFFF; color: #333333; }
```

<a name="section-selectors"></a>
## 4. Selectors

Broad selectors are too easy to abuse and will likely result in head-banging frustration. Broad selectors (e.g. `nav a {}`) may be efficient in the interim, but likely to require overriding properties farther down the cascade. Careful planning can prevent such scenarios. Use your best judgment.

* Use lowercase words separated by hyphens. Avoid underscores or camelcase formatting. *This may be unavoidable due to 3rd party scripts which inject CSS.*
* We are humans, not robots. In addition to descriptive comments, selectors may be used to describe elements (e.g. `.lead-testimonial p {}` instead of `.boxed p {}`).
* Double quotes for attribute selectors (e.g. `input[type="text"]` not `input[type='text']`).
* Avoid over-qualified selectors (e.g. `.container {}` not `div.container{}`).

**Correct:**

```css
.top-nav {
	margin: 0;
}

input[type="text"] {
	line-height: 1.2em;
}
```

**Incorrect:**

```css
.topNav { /* Avoid camelcase */
	margin: 0;
}

.top_nav { /* Avoid underscores */
	margin: 0;
}

ul.top-nav { /* Avoid over-qualification */
	margin: 0;
}

.tp-nv-r { /* Avoid robot speak */
	margin: 0;
}

input[type=text] { /* Missing double quotes around attribute */
	line-height: 1.2em;
}
```

<a name="section-properties"></a>
## Properties

There is no true right or wrong method for property ordering, but given the oppotunity, who wouldn't attempt to instill a certain logical sense of order? Meaningful & semantic trumps random chaos. Try to order properties within rulesets using the following guide:

1. Display
2. Position
3. Box Model
4. Colors & Typography
5. Other

CSS3 or vendor prefixed properties would fall under *Other*.

**Example:** *Inline comments for reference only*

```css
.navigation li {
	/* Position */
	position: absolute;
	z-index: 1;
	/* Box Model */
	padding: 10px;
	/* Colors & Typography */
	background: #333;
	color: #fff;
}
```

Order vendor prefixed properties longest to shortest (e.g. `-webkit-*` to `unprefixed`). For multi line editing, align values with spaces.

**Preferred:**

```css
.my-button {
	-webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.3);
	-moz-box-shadow:    0 1px 2px rgba(0,0,0,0.3);
	box-shadow:         0 1px 2px rgba(0,0,0,0.3);
}
```

**Not Preferred:**

```css
.my-button {
	-webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.3);
	-moz-box-shadow: 0 1px 2px rgba(0,0,0,0.3);
	box-shadow: 0 1px 2px rgba(0,0,0,0.3);
}
```