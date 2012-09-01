# Java Coding Standards

The purpose of the [47 Degrees](http://47deg.com) Java Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

Java applications developed at [47 Degrees](http://47deg.com)  should follow the [Code Conventions for the Java Programming Language](http://www.oracle.com/technetwork/java/codeconv-138413.html)

[47 Degrees](http://47deg.com)  uses the Java Programming Language and Java Related Technologies in different scenarios and applications. As a norm [47 Degrees](http://47deg.com)  follows industry standards and notifying of any deviation of this document from these standards will be welcomed.

## Table of Contents

1. [General](#section-general)
2. [Comments](#section-comments)
3. [Copyrights](#section-copyrights)
4. [Good Practices and coding habits](#section-goodpractice)

<a name="section-general"></a>
## 1. General

* All code, regardless of who touches it, should look like a single person created it.
* All culprits who ignore the aforementioned rule will be docked one pint of beer.

<a name="section-comments"></a>
## 2. Comments

Well documented Java code is as awesome as a [pizzokie](http://www.urbandictionary.com/define.php?term=pizzokie). We have all fallen victim to undocumented code; even being guilty of ignoring proper comments for our own code. Let's try and stop doing that.

At [47 Degrees](http://47deg.com)  comments in Java files should be written as [Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html).

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
 ```

<a name="section-copyrights"></a>
## 3. Copyrights

All Java files should contain the appropiate copyright notice at the beginning of the file. 

### 3.1. 47 Open Source

Open Source code written in 47 Degrees that is open source is commonly released under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html) and must be as follows.

```java
/*
 * Copyright (C) {year} 47 Degrees, LLC
 * http://47deg.com
 * hello@47deg.com
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *    http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
 ```

### 3.2. 47 Propietary - Not open sourced

Code owned and written for 47 Degrees not for open sourced projects must be as follows.

```java
/*
 * Copyright (C) {year} 47 Degrees, LLC
 * http://47deg.com
 * hello@47deg.com
 * All rights reserved
 */
 ```

### 3.3. 3rd Parties

Code owned and written for 3rd parties should be formatted in the following way.

```java
/*
 * Copyright (C) {year} {3rdPartyName}
 * {3rdPartUrl}
 * All rights reserved
 * Developed for {3rdPartyName} by:
 *
 * 47 Degrees, LLC
 * http://47deg.com
 * hello@47deg.com
 */
 ```

<a name="section-goodpractice"></a>
## 4. Good Practices and coding habits

Good practice are a must at 47 Degrees. Code is periodically reviewed for both machines and humans to ensure code quality meets standards within the company.

### 4.1. Design for interfaces

**Correct:**

```java
/**
 * Defines the contract for the user related operations 
 * @see User
 */
 public interface UserService {
 }

 /**
 * Implements the UserService connecting and saving the user to the database
 * @see UserService
 */
 public class LocalUserServiceImpl implements UserService {
 }
```

**Incorrect:**

```java
 /**
 * Implements the UserService connecting and saving the user to the database
 * @see UserService
 */
 public class UserService {
 }
```

**Correct:**

```java
public List<User> getFriends(User user) {
}
```

**Incorrect:**

```java
public ArrayList<User> getFriends(User user) {
}
```

### 4.2. Design and Architect with clear differentiation of the Application layers.

**Correct:**

```java
/**
 * User interface or API response (Serialized to JSON or used in view technologies such as JSP)
 */
 public class UserResponse {

 	private String name;

 	public UserResponse(User user) {
 		setName(user.getName());
 	}

 	public String getName() {
 		return this.name;
 	}

 	public void setName(String name) {
 		this.name = name;
 	}

 }

 /**
 * Handles UI interaction and communication to services (Servlets, Spring MVC Controllers, Android activities, Tapestry pages...)
 */
 public class UserController {

 	private UserService userService;

 	public UserResponse onCreateUserFormSubmit(String name) {
 		User user = userService.createUser(name);
 		return new UserResponse(user);
 	}

 }

 /**
 * Implements business logic (Spring Bean Services)
 */
 public interface UserService {

 	User createUser(String name);

 }

 /**
 * Implements the UserService 
 * @see UserService
 */
 public class LocalUserServiceImpl implements UserService {

 	private PersistenceAdapter persistenceAdapter;

 	public User createUser(String name) {
 		User user = new User();
 		user.setName(name);
 		persistenceAdapter.save(user);
 		return user;
 	}

 }

/**
 * Entity that gets persisted to the data store
 */
 public class User {

 	private String name;

 	public String getName() {
 		return this.name;
 	}

 	public void setName(String name) {
 		this.name = name;
 	}

 }

/**
 * Handles persistence (DAO, Cassandra Persistence Adapters, JPA Persistence Adapters)
 */
 public interface PersistenceAdapter {

 	void save(Object object);

 }
```

**Incorrect:**

```java
 /**
 * Donwloads and sorts the interwebs in a single method
 */
 public class MagicClass {
 	void doMagic(Object... args) {
 		//5000 lines here
 	}
 }
```