# CSS Coding Standards

The purpose of the 47 Degrees CSS Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing CSS to the same project. The end goal is unity, consistency, and the notion that a single entity created the outputted code.

## Table of Contents

1. [Format](#section-format)

<a name="section-format"></a>
## 1. Format

The first step to authoring consistent stylesheets begins with solid document structure and coding conventions.

* Indent each property with tabs, not spaces. Preference is tabs.
* One selector per line in multi-selector rulesets.
* Include a single space before the opening curly brace.
* Place the closing curly brace in the same column as the first character of the ruleset. 
* Include a single space after the colon of a declaration.
* Shorthand lowercase hex values (e.g. `#fff` not `#FFFFFF`).
* Use single or double quotes consistently. Preference is double quotes (e.g. `content: "";` not `content: ''`).

Correct:

```css
.selector-1,
.selector-2 {
	background: #fff;
	color: #333;
}
```

Incorrect:

```css
.selector-1, .selector-2 { background: #FFFFFF; color: #333333; }
```