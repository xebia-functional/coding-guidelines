# Java Coding Standards

The purpose of the 47 Degrees Java Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

Java applications developed at 47 Degrees should follow the Code Conventions for the Java Programming Language as outlined on http://www.oracle.com/technetwork/java/codeconv-138413.html

47 Degrees uses the Java Programming Language and Java Related Technologies in different scenarios and applications. As a norm 47 Degrees follows industry standards and notifying of any deviation of this document from these standards will be welcomed.

## Table of Contents

1. [General](#section-general)
2. [Spring](#section-comments)
3. [Android](#section-format)

<a name="section-general"></a>
## 1. General

* All code, regardless of who touches it, should look like a single person created it.
* All culprits who ignore the aforementioned rule will be docked one pint of beer.

<a name="section-comments"></a>
## 2. Comments

Well documented Java code is as awesome as a pizzokie [TextExpander](http://www.urbandictionary.com/define.php?term=pizzokie). We have all fallen victim to undocumented code; even being guilty of ignoring proper comments for our own code. Let's try and stop doing that.

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