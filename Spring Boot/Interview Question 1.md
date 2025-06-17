Video [Link](https://youtu.be/WxJi5yPuE3A?si=r2CZaOQ9G-_9csuN)
These file include most basic and very important questions of SpringBoot
### What is a spring framework? 

Spring is a java framework and an open source which is used for building enterprise Java App

### What are the core features of spring

- Inversion of Control (IOC)
- Dependency Injection (DI)
- Spring container
- Spring MVC
- Spring Data Access (ORM)
- Simplified Configuration
- Real Time capabilities

### What is Inversion of Control ?? What is Loose Coupling

Tight coupling means the two classes often change together, increasing the dependencies on both of them.

Loose coupling leads to less dependency. replacing one class will have min impact on another
##### IOC 
IoC is a design principle for create a loose coupling architecture
Here the framework will take care of the objects creation, dependency managements

### How to achieve IoC and what is diff between Principle and design pattern

Dependency injection is a design pattern to implement the IoC principle ( loose coupling )

Principles are ideas for writing better software product, going against this have negative impact on projects
Design patterns are the actual way of implementation of these principles


### What are the ways of implementing DI in spring?

##### Constructor injection
- The best and the recommended approach over others
- Used for mandatory dependencies that is provided at the obj creation
##### Field injection
- This is not recommended
- Avoid using it due to it's limitations in testability 
##### Setter function injection
- Used for optional dependency, or when the dependencies can be change after obj creation, allowing re injection if needed.
##### Method injection
- Rarely used
- For dynamic injections and it is flexible than constructor and setter injection.


### Can we use final keyword in spring boot before a variable is initialized, the variable will be updated through DI

If you are using Constructor Injection, you can do that but using other you can't do.

### What is component and @Component annotation in spring

The @Component is used to indicate that these class are managed by spring-managed component
In Spring, a component refers to a class or bean that is managed by the spring IoC

### What is a bean and what is the diff between component and bean

A spring bean class where obj that is initiated, configured and managed by the Spring IoC container, these are the building blocks of the spring app

@Bean is used to indicate the methods as bean methods which will return a bean that is managed by Spring container

Every component in spring is bean, but all the beans is not a component

### What is life cycle of bean in Spring

- Spring IoC is started
- Bean is instantiated
- Dependency is injected
- Bean is initialized
- Bean is used
- Bean is destroyed after using
![[Pasted image 20250512163649.png]]
### What is @AppConfig, @Configuration, @Component Scan 

@AppConfig is a spring config class that defines bean
@Configuration is to indicate a  file containing one or more than one bean method
### What is @Autowire annotation

@Autowire automatically injects dependencies into spring managed bean and eliminating the need for manual instantiation

