Video [Link](https://youtu.be/aW68FHrLAmA?si=G25oNwDHnM4-j2ku)

### What is Spring Boot

- A java framework make it easier to create and run java applications
- It simplifies the configuration and setup process, so that we developer can focus more on the coding part
- This is a module of Spring, allowing Rapid Application Development 

##### Problems Spring Boot solves
- Configurations
- Dependency management
- Embedded Server

### Why Spring boot over spring

##### It has more advantages over spring
- Easy to use
- Production ready Application : Metrix, Health check and features are provided for production ready application
- Rapid Development : Auto configuration allow developers to quickly develop app

### Working of Spring boot

- Spring boot start scanning starter dependency in pom.xml
- Download and auto - configure the dependency in pom.xml
- Incase of web application we will add `spring-boot-web-starter` dependency in pom.xml
- That dependency will take care of the configuration things like MVC

### How spring boot starts

- Starts with calling of main method of main class
- The run method of Spring Application is called, this starts our application
- This run method start the application's embedded server

![[Pasted image 20250510103131.png]]

### Top annotations of Spring boot

- @SpringBootApplication : this is a combination of three annotations ( @Configure, @AutoConfigure, @ComponentScan ), this is only placed on main class of the application
- @Component : this is mentioned in class level for saying that it is bean and managed by Spring bean
- @Autowired : To automate the the dependency injection in spring-managed bean
- @Service : To  mention the class represent a service component in application, this is for class containing business logic
- @RestController : Mark class as Rest controller, this is special version of @Controller that include @ResponseBody by default
- @RequestMapping : used to map URL to method with request type, this is market in method level
- @Repository : marked as DOA, used on the class that interact with the database

### What is spring boot starter dependency

- Contains collection of predefined dependencies that make easier to develop that kind of application
- These include the dependencies, version control, configuration need to make certain features of spring boot application functional

### What are the key dependencies of spring boot

- spring-boot starter parent
- spring-boot security
- spring-boot starter test
- spring-boot maven plugin
- spring-boot starter web
- spring-boot starter actuator

### Spring boot starter parent dependency

Spring Boot Starter Parent is a starter project that provides the default
configuration for spring-based applications.

- The dependency management feature manages the versions of common dependencies.
- Provide the default compiler level as Java 1.8 and UTF-8 source encoding.
- Provides a default configuration for Maven plugins such as maven-surefire-plugin, maven-jar-plugin, and maven-failsafe-plugin.
- Executes a repackage goal with a repackage execution id.
- Resource filtering and configuring profile-specific files.

### Can we use only the spring boot dependency without using the maven plugins

**Yes**
- We don't inherit from spring-boot-starter-parent pom
- Include the spring-boot-dependencies dependencies inside the dependency Management section as import scope

### What is Spring boot CLI and what are its benefits

 ##### Command line tool to create, run and manage the spring boot application
- spring 
- spring help init

### What is Thyme leaf

Java based server side template engine used in java web applications to render dynamic web pages
![[Pasted image 20250510113218.png]]