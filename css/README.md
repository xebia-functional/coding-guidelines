# CSS Coding Standards

The purpose of the 47 Degrees CSS Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing CSS to the same project. The end goal is unity, consistency, and the notion that a single entity created the outputted code.

This is a living document. The authors grow wiser with each passing day.

## Table of Contents

1. [General](#section-general)
2. [Comments](#section-comments)
3. [Format](#section-format)

<a name="section-general"></a>
## 1. General

* All code, regardless of who touches it, should look like a single person created it.
* All culprits who ignore the aforementioned rule will be docked one pint of beer.

<a name="section-comments"></a>
## 2. Comments

Well documented CSS is a double rainbow with unicorns dancing at the end near a leprechaun dance off around a pot 'o gold. We have all fallen victim to undocumented code; even being guilty of ignoring proper comments for our own code. Let's try and stop doing that.

To alleviate the ho-hum repetitive nature of continuously entering comments, configure your text editor properly (e.g. Editor Snippets or [TextExpander](http://smilesoftware.com/TextExpander/)).

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

/* #Base 960 Grid
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
* Separate rulesets with a blank line.

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