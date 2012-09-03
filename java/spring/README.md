# Spring Coding Standards

The purpose of the [47 Degrees](http://47deg.com) Spring Coding Standards is to create a collaboration baseline; helpful for scenarios where many people are creating, modifying, and contributing to the same project. The end goal is unity, consistency, and the notion that a single entity worked on the project.

This document, expected to be followed by any developers at 47 Degrees, is a subset and complement to the [Java Coding Standards](../).

## 1. Configuration

Spring is the de facto IOC container used at *47 Degrees* for Java server side applications. 
Both XML and annotation based configurations are being used.
[XML configuration](http://static.springsource.org/spring/docs/3.0.x/spring-framework-reference/html/beans.html) is favored for those services and beans that have not originally been annotated with either [@Component](http://static.springsource.org/spring/docs/3.0.x/api/org/springframework/stereotype/Component.html), [@Service](http://static.springsource.org/spring/docs/3.0.x/api/org/springframework/stereotype/Service.html), [@Controller](http://static.springsource.org/spring/docs/3.0.x/api/org/springframework/stereotype/Controller.html)... or that require certain depedencies that are easier to wire via xml.
[Annotations](http://static.springsource.org/spring/docs/3.0.x/spring-framework-reference/html/beans.html#beans-annotation-config) are preffered for Services in local packages and default Service interface implementations for applications that use package scanning to wire and discover the application context.

## 2. Services

Spring services should always be implementations of a Service interface that hides the implementations details when being used in other services dependencies.
Consider the following requirements. 

* The application needs a UserService to manipulate User model beans. 
* The User service should hide any dependencies it has in other services or 3rd party technologies.
* The service implementation could be replaced at runtime via Abstract Factories or Injection through service id qualifiers.

**Correct:**

```java
/**
 * Defines the contract for the user related operations 
 * @see User
 */
 public interface UserService {

 	void save(User user);

 }

 /**
 * Implements the UserService utilizing the Persistence Adapter for storage persistence
 * @see UserService
 */
 @Service
 public class LocalUserServiceImpl implements UserService {

 	@Autowired
 	private PersistenceAdapter persistenceAdapter;

 	@Override
 	public void save(User user) {
 		persistenceAdapter.persist(user);
 	}

 }
```

**Incorrect:**

```java
 /**
 * Utilizes the Persistence Adapter for storage persistence
 * @see UserService
 */
 @Service
 public class UserService {

 	@Autowired
 	private PersistenceAdapter persistenceAdapter;

 	@Override
 	public void save(User user) {
 		persistenceAdapter.persist(user);
 	}

 }
```


## 3. AOP

## 4. Spring MVC

### 4.1. API's

### 4.2. JSP