# Java Coding Standards

The purpose of the 47 Degrees Java Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

Java applications developed at 47 Degrees should follow the [Code Conventions for the Java Programming Language](http://www.oracle.com/technetwork/java/codeconv-138413.html)

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

Well documented Java code is as awesome as a [pizzokie](http://www.urbandictionary.com/define.php?term=pizzokie). We have all fallen victim to undocumented code; even being guilty of ignoring proper comments for our own code. Let's try and stop doing that.

At 47 Degrees comments in Java files should be written as [Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html).

An example of properly documented method method following the javadoc standard is shown below.

**Correct:**

```java

/**
 * Returns a user object that can be stored in the data store. 
 * The name argument must be alphanumeric. 
 * <p>
 * This method always creates a new user, whether or not a user 
 * with the same name already exists. 
 *
 * @param  name the name given to a new user
 * @return      the newly created user
 * @see         OtherClassOfInterest
 */
 public User createUser(String name) {
 	User user = new User();
 	user.setName(name);
 	return user;
 }

```

**Incorrect:**

```java

 // creates a user
 public User createUser(String name) {
 	User user = new User(); // a new user is always created
 	user.setName(name);
 	return user;
 }
