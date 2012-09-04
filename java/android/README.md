# Android Coding Standards

The purpose of the [47 Degrees](http://47deg.com) Android Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

This document, expected to be followed by any developers at 47 Degrees, is a subset and complement to the [Java Coding Standards](../).

## 1. Naming Conventions

Developers should pay special attention to these naming conventions as they differ from those in the standard Java Coding Conventions.

## 1.1. Resource Files

The folder *values* will have different files that will store information for our project. 
Some of the most common files and their name are

* **colors.xml**: Colors used in the application
* **config.xml**: Stores information to configure our project (ex. keys for services, urls, etc)
* **dimen.xml**: Dimensions used in application (ex. action bar height , paddings, etc)
* **strings.xml**: Localizable strings
* **plurals.xml**: Plurals. Contains references to strings.xml
* **arrays.xml**: Arrays. Contains references to strings.xml 

## 1.3. Java Packages & Class Names

An android App should generally follow the following package structure

* com.company.product.android
	- **activities**: All Activities with the word Activity pre-fixed by the Activity name: *[Name]*Activity e.g. MainActivity
	- **adapters**: All Adapters with the word Adapter pre-fixed by the Adapter name: *[Name]*Adapter e.g. UserListAdapter
	- **services**: All Services including API clients and other persistence related services e.g. UserService
	- **components**: All reusable components utilized in Activity and Fragments e.g. UserProfileComponent
	- **dialogs**: All Fragment Dialogs with the word Dialog pre-fixed by the dialog name: *[Name]*Dialog e.g. DeleteAccountConfirmationDialog
	- **fragments**: All Fragments with the word Fragment pre-fixed by the Fragment name: *[Name]*Fragment e.g. UserMapLocationFragment
	- **utils**: All cross package utilities with the word Utils pre-fixed by the Utility name: *[Name]*Utils e.g. StringUtils