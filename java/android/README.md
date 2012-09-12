# Android Coding Standards

The purpose of the [47 Degrees](http://47deg.com) Android Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

This document, expected to be followed by any developers at 47 Degrees, is a subset and complement to the [Java Coding Standards](../).

**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Android Coding Standards](#android-coding-standards)
	- [1. Naming Conventions](#1-naming-conventions)
		- [1.1. Common Resource Files](#11-common-resource-files)
		- [1.2. Java Packages & Class Names](#12-java-packages--class-names)
		- [1.3. Resource Names](#13-resource-names)
		- [1.4. String Resources](#14-string-resources)
		- [1.5. Style Resources](#15-style-resources)
 		- [1.6. Dimen Resources](#16-dimen-resources)
	- [2. Conventions for devices 7 inches](#2-conventions-for-devices-7-inches)

## 1. Naming Conventions

Developers should pay special attention to these naming conventions as they differ from those in the standard Java Coding Conventions.

### 1.1. Common Resource Files

The folder *values* will have different files that will store information for our project. 
Some of the most common files and their name are

* **colors.xml**: Colors used in the application
* **config.xml**: Stores information to configure our project (ex. keys for services, urls, etc)
* **dimen.xml**: Dimensions used in application (ex. action bar height , paddings, etc)
* **strings.xml**: Localizable strings
* **plurals.xml**: Plurals. Contains references to strings.xml
* **arrays.xml**: Arrays. Contains references to strings.xml 

### 1.2. Java Packages & Class Names

An android App should generally follow the following package structure

* **com.company.product.android**
	- **activities**: All Activities with the word Activity pre-fixed by the Activity name: *[Name]*Activity e.g. MainActivity
	- **adapters**: All Adapters with the word Adapter pre-fixed by the Adapter name: *[Name]*Adapter e.g. UserListAdapter
	- **services**: All Services including API clients and other persistence related services e.g. UserService
	- **components**: All reusable components utilized in Activity and Fragments e.g. UserProfileComponent
	- **dialogs**: All Fragment Dialogs with the word Dialog pre-fixed by the dialog name: *[Name]*Dialog e.g. DeleteAccountConfirmationDialog
	- **fragments**: All Fragments with the word Fragment pre-fixed by the Fragment name: *[Name]*Fragment e.g. UserMapLocationFragment
	- **utils**: All cross package utilities with the word Utils pre-fixed by the Utility name: *[Name]*Utils e.g. StringUtils

### 1.3. Resource Names

The following structure should be followed when naming resoures.

**group** _ **type** _ **name** _ *[state]* _ *[suffix]*

* **Group**: Application area or screen. If the resource is used in different parts of applications 'common' should be used instead. e.g. actionbar, menu, media, popup, footer, audio, etc.
* **Type**: Resource Type. e.g. background, icon, button, textfield, list, menuitem, radiobutton, checkbox, tab, dialog, title, etc.
* **Name**: Descriptive name as to what the resource is about. e.g. play, stop.
* **State**: (Optional): The optional state of a parent resource. e.g. A button could be in 'normal', 'pressed', 'disabled' and 'selected'. A checkbox could be 'on' or 'off'. These resources should NEVER be used directly in layout but rather as state selectors.
* **Suffix**: (Optional): An arbitrary suffix that helps to further identify a property of the resource. e.g. bright, dark, opaque, layer.

Below are some examples of properly named resources.

* common_background_app
* audio_icon_play_on
* common_icon_preferences
* actionbar_button_send (XML resource)
	- action_button_send_normal
	- action_button_send_pressed
	- action_button_send_disabled

### 1.4. String Resources

String resources placed in xml resources files such as strings.xml, config.xml, etc. are named following the same convention as Java naming conventions for variables and fields. CamelCase with the first letter lowercased.

Below are some examples of properly named string identifiers.

* serverApiUrl
* phoneNumber
* services
* url

### 1.5. Style Resources

String resources placed in styles.xml are named in CamelCase.
The following structure should be followed when naming style resoures.

**[Group]TypeName[Suffix]**

* **Group** (Optional): Application area or screen. e.g. actionbar, menu, media, popup, footer, audio.
* **Type**: Resource Type. e.g. Background, Icon, Button, Textfield, List, MenuItem, RadioButton, Checkbox, Tab, Dialog.
* **Name**: Descriptive name as to what the resource is about. e.g. play, stop.
* **Suffix**: (Optional): An arbitrary suffix that helps to further identify a property of the resource. e.g. Bright, Dark, Opaque, Layer.

Below are some examples of properly named string identifiers.

* ButtonSend
* ActionBarButtonBack
* ListTitle

### 1.6. Dimen Resources

Dimens resources placed in dimen.xml. The following structure should be followed when naming dimentions.

**property** _ **default** _ **group** _ **type** _ **name**

* **property**: Type of property reference. e.g. font_size, padding, margin, height, width.
* **default** (Optional): Write "default" if is a general dimen.
* **group** (Optional): Application area or screen. e.g. action_bar, menu, popup, wizard.
* **type** (Optional): Type of resource. e.g. button, title, text, edittext.
* **name** (Optional): Only if is necessary.

Below are some examples.

* padding_default
* font_size_action_bar_button
* height_default_action_bar

We should have some dimension in all projects by default. These are:

* padding_default
* margin_default
* font_size_default_button
* font_size_default_title
* font_size_default_text
* height_default_action_bar
* font_size_default_action_bar

## 2. Conventions for 7" devices

7" devices require a special treatment. The problem is that these devices usually use "mdpi" as default density.

These are the consideration to follow when targeting apps in these devices

* Copy hdpi drawables to "drawable-sw600dp-mdpi".
* Create a new dimensions file for this screens. The file "dimen.xml" will be in the "values-sw600dp-mdpi" folder. Usually the dimensions will be at 150%. All fonts sizes should be in dimen.xml file as well.
