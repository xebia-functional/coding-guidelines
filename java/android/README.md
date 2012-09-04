# Android Coding Standards

The purpose of the [47 Degrees](http://47deg.com) Android Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

This document, expected to be followed by any developers at 47 Degrees, is a subset and complement to the [Java Coding Standards](../).

## 1. Naming Conventions

Developers should pay special attention to these naming conventions as they differ from those in the standard Java Coding Conventions.

## 1.1. Java files

Follow the same naming conventions in the [Java Coding Standards](../).

## 1.2. Resource files

The folder *values* will have different files that will store information for our project. 
Some of the most common files and their name are

* **colors.xml**: Colors used in the application
* **config.xml**: Stores information to configure our project (ex. keys for services, urls, etc)
* **dimen.xml**: Dimensions used in application (ex. action bar height , paddings, etc)
* **strings.xml**: Localizable strings
* **plurals.xml**: Plurals. Contains references to strings.xml
* **arrays.xml**: Arrays. Contains references to strings.xml 