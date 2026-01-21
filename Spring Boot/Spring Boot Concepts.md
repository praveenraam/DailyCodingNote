Next File : [[Interview Question 1]]
## Dependency Injection (DI) and Inversion of Control (IoC) Overview

**Dependency Injection (DI)**:

- A design pattern used to implement IoC.
- Dependencies (objects a class needs to function) are provided to a class rather than the class creating them itself.
- Helps in creating loosely coupled and easily testable code.

**Inversion of Control (IoC)**:

- A principle where the control of object creation and management is inverted from the class itself to a container or framework.
- Promotes loose coupling by ensuring that objects do not create their dependencies.

### Simple Example

#### Without Dependency Injection

```java
class Car {
    private Engine engine;

    public Car() {
        this.engine = new Engine(); // Car creates its own Engine
    }

    public void start() {
        engine.run();
    }
}

class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start();
    }
}
```

**Problems**:

- Car is tightly coupled to Engine.
- Hard to test Car independently of Engine.

#### With Dependency Injection

```java
class Car {
    private Engine engine;

    // Engine is injected through the constructor
    public Car(Engine engine) {
        this.engine = engine;
    }

    public void start() {
        engine.run();
    }
}

class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

public class Main {
    public static void main(String[] args) {
        Engine engine = new Engine();
        Car car = new Car(engine); // Injecting Engine into Car
        car.start();
    }
}
```

**Benefits**:

- Car and Engine are loosely coupled.
- Easy to test Car by injecting a mock Engine.

#### Using a DI Framework (e.g., Spring)

```java
import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

class Car {
    private Engine engine;

    public Car(Engine engine) {
        this.engine = engine;
    }

    public void start() {
        engine.run();
    }
}

class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

@Configuration
class Config {
    @Bean
    public Engine engine() {
        return new Engine();
    }

    @Bean
    public Car car(Engine engine) {
        return new Car(engine);
    }
}

public class Main {
    public static void main(String[] args) {
        ApplicationContext context = new AnnotationConfigApplicationContext(Config.class);
        Car car = context.getBean(Car.class);
        car.start();
    }
}
```

**Advantages of Using a Framework**:

- The framework manages the creation and injection of dependencies.
- Enhances modularity and testability.
- Simplifies configuration and reduces boilerplate code.

### Key Points

- **Loose Coupling**: DI and IoC promote loose coupling between classes.
- **Testability**: Easier to test classes in isolation.
- **Flexibility**: Classes can be reused and configured in different ways without changing their code.

Using DI and IoC effectively helps in building scalable, maintainable, and testable applications.

## In-Depth Explanation of Dependency Injection

**Dependency Injection (DI)**:

- A design pattern used to achieve Inversion of Control (IoC) between classes and their dependencies.
- Instead of the class creating its dependencies, they are provided to the class externally.
- Promotes loose coupling, easier testing, and better maintainability.

### Types of Dependency Injection

1. **Constructor Injection**: Dependencies are provided through the class constructor.
2. **Setter Injection**: Dependencies are provided through setter methods.
3. **Field Injection**: Dependencies are injected directly into fields.

### Example Classes: Car and Engine

Let's create a simple example using `Car` and `Engine` classes to demonstrate constructor, setter, and field injection using Spring's `@Autowired` annotation.

#### 1. Constructor Injection

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

@Component
class Car {
    private Engine engine;

    // Constructor injection
    public Car(Engine engine) {
        this.engine = engine;
    }

    public void start() {
        engine.run();
    }
}

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@ComponentScan(basePackages = "your.example.code")
class AppConfig {}

public class Main {
    public static void main(String[] args) {
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        Car car = context.getBean(Car.class);
        car.start();
    }
}
```

#### 2. Setter Injection

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

@Component
class Car {
    private Engine engine;

    @Autowired
    public void setEngine(Engine engine) {
        this.engine = engine;
    }

    public void start() {
        engine.run();
    }
}

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@ComponentScan(basePackages = "your.example.code")
class AppConfig {}

public class Main {
    public static void main(String[] args) {
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        Car car = context.getBean(Car.class);
        car.start();
    }
}
```

#### 3. Field Injection

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
class Engine {
    public void run() {
        System.out.println("Engine is running");
    }
}

@Component
class Car {
    @Autowired
    private Engine engine;

    public void start() {
        engine.run();
    }
}

import org.springframework.context.ApplicationContext;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;

@Configuration
@ComponentScan(basePackages = "your.example.code")
class AppConfig {}

public class Main {
    public static void main(String[] args) {
        ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        Car car = context.getBean(Car.class);
        car.start();
    }
}
```

### How Dependency Injection Works in Spring

1. **Spring Container**: Manages the lifecycle of beans (objects) and their dependencies.
2. **Annotations**: Use annotations like `@Component`, `@Autowired`, and `@Configuration` to define beans and inject dependencies.
3. **Component Scanning**: Automatically detects and registers beans defined in the specified packages.
4. **Autowiring**: Automatically resolves and injects dependencies into beans using `@Autowired`.

### Key Points

- **Constructor Injection** is preferred for mandatory dependencies and makes the class immutable.
- **Setter Injection** is useful for optional dependencies.
- **Field Injection** is quick and convenient but can make the code less transparent and harder to test.
- **Spring Framework** provides powerful support for DI through annotations, making it easier to manage dependencies and configurations.

## JavaBeans

**JavaBeans** are reusable software components for Java that can be manipulated visually in a builder tool. They follow specific conventions to ensure they are easy to manipulate and integrate with various tools and frameworks.

##### Key Characteristics of JavaBeans:

1. **Properties**:

   - Private fields.
   - Public getter and setter methods for accessing and modifying the properties.

2. **No-Argument Constructor**:

   - A no-argument constructor is required to allow easy instantiation and configuration.

3. **Serializable**:

   - JavaBeans should implement `Serializable` to allow their state to be saved and restored, although this is not a strict requirement.

4. **Methods**:

   - Getter and setter methods follow the naming conventions `get<PropertyName>` and `set<PropertyName>` for properties.
   - Boolean properties may use `is<PropertyName>` instead of `get<PropertyName>`.

5. **Events**:
   - JavaBeans can have methods to add and remove event listeners, enabling other components to register interest in events generated by the bean.

##### Example of a JavaBean

```java
import java.io.Serializable;

public class EmployeeBean implements Serializable {
    private String name;
    private int age;

    // No-argument constructor
    public EmployeeBean() {}

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        this.age = age;
    }

    // toString method
    @Override
    public String toString() {
        return "EmployeeBean{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

## Serialization

**Serialization** is the process of converting an object's state into a byte stream, enabling the object to be easily saved to a file, sent over a network, or stored in a database. The reverse process, **deserialization**, reconstructs the object from the byte stream.

##### Key Points of Serialization:

1. **Serializable Interface**:

   - A class must implement the `Serializable` interface to be serializable.
   - This interface is a marker interface (it does not contain any methods).

2. **transient Keyword**:

   - Fields marked as `transient` are not serialized.

3. **serialVersionUID**:
   - A unique identifier for each Serializable class.
   - Used during deserialization to ensure that a loaded class corresponds exactly to a serialized object.

##### Example of Serialization

```java
import java.io.*;

public class SerializeExample {
    public static void main(String[] args) {
        EmployeeBean employee = new EmployeeBean();
        employee.setName("John Doe");
        employee.setAge(30);

        // Serialization
        try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("employee.ser"))) {
            out.writeObject(employee);
        } catch (IOException e) {
            e.printStackTrace();
        }

        // Deserialization
        try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("employee.ser"))) {
            EmployeeBean deserializedEmployee = (EmployeeBean) in.readObject();
            System.out.println("Deserialized Employee: " + deserializedEmployee);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

### Can You Create a JavaBean Without Getters, Setters, or Being Serializable?

#### Without Getters and Setters:

Technically, you can create a class without getters and setters, but it would not conform to the JavaBeans specification. JavaBeans require getters and setters to allow properties to be accessed and modified in a standardized way, particularly by frameworks and tools that rely on these conventions.

#### Without Serialization:

Yes, a JavaBean can be created without implementing `Serializable`. Serialization is recommended for JavaBeans to allow their state to be easily saved and restored, but it is not a strict requirement. However, omitting serialization may limit the bean's usability in certain contexts where saving the state of the bean is necessary.

##### Example of a Non-Serializable JavaBean Without Getters and Setters

```java
public class SimpleBean {
    public String name;
    public int age;

    // No-argument constructor
    public SimpleBean() {}

    // Constructor with parameters
    public SimpleBean(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

In this example, `SimpleBean` does not conform to the JavaBeans specification because it lacks private fields, getters, and setters, and does not implement `Serializable`. While it may function as a simple Java object, it will not integrate well with tools and frameworks designed to work with JavaBeans.

## POJO

A POJO (Plain Old Java Object) is a simple Java object that is free from any particular conventions or restrictions beyond those imposed by the Java language itself. Here’s a more detailed explanation of what a POJO should be and what it should not do.

### What a POJO Should Be:

1. **Plain**: The class should be a regular Java class with no special requirements.
2. **Private Fields**: Fields should be private to encapsulate the data.
3. **Public Getters and Setters**: Provide public methods to access and modify the fields.
4. **Serializable (optional)**: It can implement the `Serializable` interface if needed, but it is not mandatory.
5. **Constructors**: It can have constructors, including a no-argument constructor, but having constructors is not a requirement.

### What a POJO Should Not Do:

1. **No Specific Inheritance**: It should not extend classes or implement interfaces from frameworks (e.g., it should not extend `HttpServlet` or implement `Remote`).
2. **No Annotations**: It should not have annotations that force it to comply with a framework (e.g., `@Entity` from JPA or `@Component` from Spring).
3. **No Framework Dependencies**: It should not have dependencies on specific frameworks or libraries.
4. **No Business Logic**: Typically, POJOs do not contain business logic; they are used for holding data.

### Example of a Proper POJO

```java
public class Product {
    private String id;
    private String name;
    private double price;

    // No-argument constructor
    public Product() {}

    // Constructor with parameters
    public Product(String id, String name, double price) {
        this.id = id;
        this.name = name;
        this.price = price;
    }

    // Getter for id
    public String getId() {
        return id;
    }

    // Setter for id
    public void setId(String id) {
        this.id = id;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for price
    public double getPrice() {
        return price;
    }

    // Setter for price
    public void setPrice(double price) {
        this.price = price;
    }

    // toString method
    @Override
    public String toString() {
        return "Product{" +
                "id='" + id + '\'' +
                ", name='" + name + '\'' +
                ", price=" + price +
                '}';
    }
}
```

### What a POJO Should Not Be:

#### Incorrect Example (Not a POJO)

```java
import javax.persistence.Entity;
import javax.persistence.Id;

@Entity
public class ProductEntity {
    @Id
    private String id;
    private String name;
    private double price;

    // Getters and Setters
}
```

### Why the Above Example is Not a POJO:

1. **Annotations**: The class uses `@Entity` and `@Id` annotations, which tie it to the JPA framework.
2. **Specific Dependencies**: It has dependencies on JPA (Java Persistence API), which makes it non-plain.

By ensuring your class remains plain and free from specific framework dependencies, you maintain its simplicity and flexibility, making it a true POJO.

Sure! Here's a simple example to illustrate a POJO (Plain Old Java Object) class in Java, along with its definition. Following that, we'll convert it to a JavaBean.

### JavaBean Class Definition

A **JavaBean** is a special type of POJO that follows certain conventions:

- It should have a no-argument constructor.
- Properties should be private with public getters and setters.
- It should be serializable (though this is often implied).

### Example of a JavaBean Class

```java
import java.io.Serializable;

public class UserBean implements Serializable {
    private String name;
    private int age;

    // No-argument constructor
    public UserBean() {}

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        this.age = age;
    }

    // toString method
    @Override
    public String toString() {
        return "UserBean{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

### Key Differences:

1. **No-Argument Constructor**: The JavaBean has a no-argument constructor, which is required for it to be a valid bean.
2. **Serialization**: Although not always explicitly required, JavaBeans are typically serializable.

Both classes are quite similar, but following these additional rules makes the second class a JavaBean.

## Spring MVC Detailed Notes

#### Overview

Spring MVC (Model-View-Controller) is a web framework designed around the MVC design pattern. It separates the application into three main components:

1. **Model**: Encapsulates the application's data and business logic.
2. **View**: Handles the presentation layer and UI.
3. **Controller**: Manages the application's request handling and acts as an intermediary between Model and View.

### Flow of Client request into spring app

```Java
Client
  ↓
Servlet Container (Tomcat)
  ↓
Filters (including Spring Security filters)
  ↓
DispatcherServlet
  ↓
Handler Mapping
  ↓
Interceptors (preHandle)
  ↓
Controller
  ↓
Interceptors (postHandle / afterCompletion)
  ↓
Response goes back (reverse order)
```

#### Core Concepts

1. **Front Controller (DispatcherServlet)**

   - The `DispatcherServlet` is the central servlet that receives all HTTP requests and delegates them to appropriate controllers.
   - It configures the web application context and resolves views.
   - Configuration example in `web.xml`:
     ```xml
     <servlet>
         <servlet-name>dispatcher</servlet-name>
         <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
         <load-on-startup>1</load-on-startup>
     </servlet>
     <servlet-mapping>
         <servlet-name>dispatcher</servlet-name>
         <url-pattern>/</url-pattern>
     </servlet-mapping>
     ```

2. **Controller**

   - Controllers handle user requests and return the appropriate view along with a model.
   - They are annotated with `@Controller`.
   - Example:

     ```java
     @Controller
     public class HomeController {

         @RequestMapping("/home")
         public String home(Model model) {
             model.addAttribute("message", "Welcome to Spring MVC");
             return "home";  // View name
         }
     }
     ```

3. **RequestMapping**

   - `@RequestMapping` is used to map web requests to specific handler methods.
   - It can be applied at both class and method levels.
   - Example:
     ```java
     @RequestMapping(value = "/user", method = RequestMethod.GET)
     public String getUser(Model model) {
         // Handle GET request
         return "user";
     }
     ```

4. **Model**

   - The `Model` interface is used to pass data from the controller to the view.
   - Data can be added to the model using `addAttribute`.
   - Example:
     ```java
     model.addAttribute("attributeName", attributeValue);
     ```

5. **View Resolver**

   - A `ViewResolver` resolves logical view names to actual view implementations.
   - Example configuration in `applicationContext.xml`:
     ```xml
     <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
         <property name="prefix" value="/WEB-INF/views/" />
         <property name="suffix" value=".jsp" />
     </bean>
     ```

6. **Repository**

   - Repository in Spring is a mechanism for encapsulating storage, retrieval, and search behavior which emulates a collection of objects.
   - It is typically annotated with `@Repository`.
   - Example:
     ```java
     @Repository
     public interface UserRepository extends JpaRepository<User, Long> {
     }
     ```

7. **Service**

   - The service layer contains the business logic.
   - Services are annotated with `@Service`.
   - Example:

     ```java
     @Service
     public class UserService {

         @Autowired
         private UserRepository userRepository;

         public User findUserById(Long id) {
             return userRepository.findById(id).orElse(null);
         }
     }
     ```

8. **Dependency Injection**

   - Spring's core feature is dependency injection (DI), which allows for loose coupling between components.
   - Components are injected using `@Autowired`, `@Inject`, or via constructor injection.
   - Example:

     ```java
     @Controller
     public class HomeController {

         private final UserService userService;

         @Autowired
         public HomeController(UserService userService) {
             this.userService = userService;
         }

         @RequestMapping("/user/{id}")
         public String getUser(@PathVariable Long id, Model model) {
             User user = userService.findUserById(id);
             model.addAttribute("user", user);
             return "user";
         }
     }
     ```

9. **Form Handling**

   - Spring MVC provides support for form handling through `@ModelAttribute` and `@RequestParam`.
   - Example:

     ```java
     @Controller
     public class UserController {

         @GetMapping("/register")
         public String showForm(Model model) {
             model.addAttribute("user", new User());
             return "register";
         }

         @PostMapping("/register")
         public String submitForm(@ModelAttribute User user) {
             // Handle form submission
             return "result";
         }
     }
     ```

10. **Exception Handling**

    - Spring MVC allows handling exceptions using `@ExceptionHandler`, `@ControllerAdvice`, or by defining custom error pages.
    - Example:

      ```java
      @ControllerAdvice
      public class GlobalExceptionHandler {

          @ExceptionHandler(UserNotFoundException.class)
          public String handleUserNotFound(Model model) {
              model.addAttribute("error", "User not found");
              return "error";
          }
      }
      ```

11. **Interceptors**

    - Interceptors can be used to pre-handle and post-handle requests.
    - pre handle is done before the controller comes to the picture ensuring all the check are properly done with logging process
    - Post handle add some common response attributes and logging
    - Example:

      ```java
      public class LoggingInterceptor implements HandlerInterceptor {

          @Override
          public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
              // Pre-handle logic
              return true;
          }

          @Override
          public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView) throws Exception {
              // Post-handle logic
          }

          @Override
          public void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex) throws Exception {
              // After completion logic
          }
      }
      ```

    - Configuration:

      ```java
      @Configuration
      public class WebConfig implements WebMvcConfigurer {

          @Override
          public void addInterceptors(InterceptorRegistry registry) {
              registry.addInterceptor(new LoggingInterceptor());
          }
      }
      ```

By understanding and implementing these concepts, you can build robust, maintainable, and scalable web applications using Spring MVC.

## Hibernate , JPA

Hibernate, JPA, and Spring Data JPA are all frameworks used for interacting with relational databases in Java applications.

**Hibernate** is an Object-Relational Mapping (ORM) framework that provides a high-level API for interacting with relational databases. It allows you to map Java objects to database tables and perform database operations using a high-level API, instead of writing low-level SQL code.

**JPA** (Java Persistence API) is a specification that defines a set of interfaces and annotations for working with relational databases in Java applications. JPA provides a common API for ORM frameworks like Hibernate, EclipseLink, and OpenJPA, making it easier to switch between different ORM frameworks without changing your code.

**Spring Data JPA** is a part of the Spring Framework that provides a higher-level, easier-to-use API for working with JPA. It reduces the amount of boilerplate code required to interact with a database using JPA, and provides a repository abstraction that provides a number of methods out of the box for performing CRUD operations on JPA entities.

In summary, Hibernate is an ORM framework that provides a high-level API for interacting with databases, JPA is a specification that defines a common API for ORM frameworks like Hibernate, and Spring Data JPA is a part of the Spring Framework that provides a higher-level, easier-to-use API for working with JPA.

## What is in JPA, how it actually look?

JPA (Java Persistence API) is a specification that defines a set of APIs and annotations for working with relational databases in Java applications. JPA provides a common API for ORM (Object-Relational Mapping) frameworks like Hibernate, Eclipse Link, and OpenJPA, making it easier to switch between different ORM frameworks without changing your code.

Here is an example of how JPA looks in a Java application:

```java
import javax.persistence.*;

@Entity
@Table(name = "users")
public class User {

  @Id
  @GeneratedValue(strategy = GenerationType.IDENTITY)
  private Long id;

  @Column(name = "name")
  private String name;

  @Column(name = "email")
  private String email;

  public User() {}

  public User(String name, String email) {
    this.name = name;
    this.email = email;
  }

  // getters and setters

  @Override
  public String toString() {
    return id + ": " + name + " (" + email + ")";
  }
}
```

In this example, the `User` class is annotated with JPA annotations that define how the Java object should be mapped to a database table.

The `@Entity` annotation marks this class as a JPA entity, which means that it can be persisted to a relational database. The `@Table` annotation specifies the name of the database table to map to.

The `@Id` annotation marks the `id` field as the primary key of the table, and the `@GeneratedValue` annotation specifies how the primary key value should be generated. In this case, it is set to `GenerationType.IDENTITY`, which means that the database will automatically generate a value for this field.

The `@Column` annotation specifies the name of the database column to map to, for the `name` and `email` fields.

JPA provides many other annotations and APIs for defining object-relational mappings, managing entities, performing queries, and transaction management. By using JPA, you can write Java code that interacts with a database using a high-level API, without having to write low-level SQL code.

Sure! Let's break down the CRUD operations into simpler examples for each approach: without Hibernate, with Hibernate, and with Spring Data JPA. We'll use the same database schema for consistency.

### Without Hibernate (using JDBC)

1. **Create:**

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class CreateExample {
    private static final String DB_URL = "jdbc:mysql://localhost/mydatabase";
    private static final String DB_USER = "myuser";
    private static final String DB_PASSWORD = "mypassword";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD)) {
            String insertQuery = "INSERT INTO users (name, email) VALUES (?, ?)";
            PreparedStatement pstmt = conn.prepareStatement(insertQuery);
            pstmt.setString(1, "John Doe");
            pstmt.setString(2, "johndoe@example.com");
            int rowsAffected = pstmt.executeUpdate();
            System.out.println("Inserted " + rowsAffected + " row(s).");
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

2. **Read:**

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class ReadExample {
    private static final String DB_URL = "jdbc:mysql://localhost/mydatabase";
    private static final String DB_USER = "myuser";
    private static final String DB_PASSWORD = "mypassword";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD)) {
            String selectQuery = "SELECT * FROM users WHERE id = ?";
            PreparedStatement pstmt = conn.prepareStatement(selectQuery);
            pstmt.setInt(1, 1);
            ResultSet rs = pstmt.executeQuery();
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                String email = rs.getString("email");
                System.out.println(id + ": " + name + " (" + email + ")");
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

3. **Update:**

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class UpdateExample {
    private static final String DB_URL = "jdbc:mysql://localhost/mydatabase";
    private static final String DB_USER = "myuser";
    private static final String DB_PASSWORD = "mypassword";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD)) {
            String updateQuery = "UPDATE users SET email = ? WHERE id = ?";
            PreparedStatement pstmt = conn.prepareStatement(updateQuery);
            pstmt.setString(1, "newemail@example.com");
            pstmt.setInt(2, 1);
            int rowsAffected = pstmt.executeUpdate();
            System.out.println("Updated " + rowsAffected + " row(s).");
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

4. **Delete:**

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DeleteExample {
    private static final String DB_URL = "jdbc:mysql://localhost/mydatabase";
    private static final String DB_USER = "myuser";
    private static final String DB_PASSWORD = "mypassword";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD)) {
            String deleteQuery = "DELETE FROM users WHERE id = ?";
            PreparedStatement pstmt = conn.prepareStatement(deleteQuery);
            pstmt.setInt(1, 1);
            int rowsAffected = pstmt.executeUpdate();
            System.out.println("Deleted " + rowsAffected + " row(s).");
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### With Hibernate

1. **Create:**

```java
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

public class CreateExample {
    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("myPersistenceUnit");
        EntityManager em = emf.createEntityManager();
        EntityTransaction tx = em.getTransaction();

        try {
            tx.begin();
            User user = new User("John Doe", "johndoe@example.com");
            em.persist(user);
            tx.commit();
            System.out.println("Inserted user: " + user);
        } catch (Exception e) {
            if (tx.isActive()) {
                tx.rollback();
            }
            e.printStackTrace();
        } finally {
            em.close();
            emf.close();
        }
    }
}
```

2. **Read:**

```java
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.Persistence;

public class ReadExample {
    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("myPersistenceUnit");
        EntityManager em = emf.createEntityManager();

        try {
            User user = em.find(User.class, 1L);
            System.out.println(user);
        } finally {
            em.close();
            emf.close();
        }
    }
}
```

3. **Update:**

```java
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

public class UpdateExample {
    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("myPersistenceUnit");
        EntityManager em = emf.createEntityManager();
        EntityTransaction tx = em.getTransaction();

        try {
            tx.begin();
            User user = em.find(User.class, 1L);
            user.setEmail("newemail@example.com");
            tx.commit();
            System.out.println("Updated user: " + user);
        } catch (Exception e) {
            if (tx.isActive()) {
                tx.rollback();
            }
            e.printStackTrace();
        } finally {
            em.close();
            emf.close();
        }
    }
}
```

4. **Delete:**

```java
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

public class DeleteExample {
    public static void main(String[] args) {
        EntityManagerFactory emf = Persistence.createEntityManagerFactory("myPersistenceUnit");
        EntityManager em = emf.createEntityManager();
        EntityTransaction tx = em.getTransaction();

        try {
            tx.begin();
            User user = em.find(User.class, 1L);
            em.remove(user);
            tx.commit();
            System.out.println("Deleted user: " + user);
        } catch (Exception e) {
            if (tx.isActive()) {
                tx.rollback();
            }
            e.printStackTrace();
        } finally {
            em.close();
            emf.close();
        }
    }
}
```

### With Spring Data JPA

1. **Create:**

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class CreateExample implements CommandLineRunner {

    @Autowired
    private UserRepository userRepository;

    public static void main(String[] args) {
        SpringApplication.run(CreateExample.class, args);
    }

    @Override
    public void run(String... args) {
        User user = new User("John Doe", "johndoe@example.com");
        userRepository.save(user);
        System.out.println("Inserted user: " + user);
    }
}
```

2. **Read:**

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ReadExample implements CommandLineRunner {

    @Autowired
    private UserRepository userRepository;

    public static void main(String[] args) {
        SpringApplication.run(ReadExample.class, args);
    }

    @Override
    public void run(String... args) {
        User user = userRepository.findById(1L).orElse(null);
        System.out.println(user);
    }
}
```

3. **Update:**

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class UpdateExample implements CommandLineRunner {

    @Autowired
    private UserRepository userRepository;

    public static void main(String[] args) {
        SpringApplication.run(UpdateExample.class, args);
    }

    @Override
    public void run(String... args) {
        User user = userRepository.findById(1L).orElse(null);
        if (user != null) {
            user.setEmail("newemail@example.com");
            userRepository.save(user);
            System.out.println("Updated user: " + user);
        }
    }
}
```

4. **Delete:**

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DeleteExample implements CommandLineRunner {

    @Autowired
    private UserRepository userRepository;

    public static void main(String[] args) {
        SpringApplication.run(DeleteExample.class, args);
    }

    @Override
    public void run(String... args) {
        User user

 = userRepository.findById(1L).orElse(null);
        if (user != null) {
            userRepository.delete(user);
            System.out.println("Deleted user: " + user);
        }
    }
}
```

In summary, Spring Data JPA simplifies the process by reducing boilerplate code, making it easier to interact with the database compared to JDBC and Hibernate. Each approach has its use cases and can be chosen based on the project's complexity and requirements.

## Here are 15 popular **JPA** annotations:

1. `@Entity`: Marks a Java class as a JPA entity, which can be persisted to a database.
2. `@Table`: Specifies the name of the database table to map the entity to.
3. `@Id`: Specifies the primary key field of the entity.
4. `@GeneratedValue`: Specifies how the primary key value should be generated.
5. `@Column`: Specifies the mapping of the entity field to a database column.
6. `@JoinColumn`: Specifies the mapping of a foreign key column between two entities.
7. `@OneToOne`: Defines a one-to-one relationship between two entities.
8. `@OneToMany`: Defines a one-to-many relationship between two entities.
9. `@ManyToOne`: Defines a many-to-one relationship between two entities.
10. `@ManyToMany`: Defines a many-to-many relationship between two entities.
11. `@NamedQuery`: Defines a named query for an entity.
12. `@NamedQueries`: Defines a set of named queries for an entity.
13. `@Transient`: Specifies that an entity field should not be persisted to the database.
14. `@Version`: Specifies the version field of the entity, used for optimistic locking.
15. `@Temporal`: Specifies the temporal type of a date or timestamp entity field.

These are just a few of the many JPA annotations available. Depending on your use case, you may need to use additional annotations.

## Here are a few Hibernate annotations that are not part of the JPA specification:

1. `@Proxy(lazy = false)`: Specifies that an entity should not be lazily loaded.
2. `@Type`: Specifies the type of a Hibernate-specific custom type for an entity field.
3. `@Fetch`: Specifies the fetch mode for a related entity or collection.
4. `@BatchSize`: Specifies the batch size for fetching related entities or collections.
5. `@SQLInsert`, `@SQLUpdate`, `@SQLDelete`: Specifies the SQL statements for inserting, updating, or deleting an entity.
6. `@Formula`: Specifies a derived property of an entity using an SQL expression.
7. `@DynamicUpdate`, `@DynamicInsert`: Specifies that only the modified properties should be included in the SQL update or insert statement.

These annotations provide additional functionality and flexibility that is not available in the JPA specification. However, using Hibernate-specific annotations can make your code less portable, as it becomes tied to the Hibernate implementation. To maximize portability, it’s recommended to use only JPA annotations and avoid using Hibernate-specific annotations unless necessary.

## Here are some Spring Data JPA-specific annotations:

1. `@Repository`: Marks the interface as a Spring Data JPA repository.
2. `@Query`: Defines a custom JPQL or native SQL query for an entity.
3. `@NamedQuery`: Defines a named query for an entity.
4. `@Param`: Binds a method parameter to a named parameter in a custom query.
5. `@Lock`: Specifies the lock mode to use when fetching an entity.
6. `@EntityGraph`: Specifies the entity graph to use when fetching an entity.
7. `@Procedure`: Specifies the name of a stored procedure to call.
8. `@ProcedureParameter`: Specifies a parameter for a stored procedure.
9. `@EnableJpaRepositories`: Enables Spring Data JPA repositories in a Spring Boot application.
10. `@Transactional`: Specifies that a method should be executed within a transaction.

These annotations are used to define custom queries, specify lock modes and entity graphs, and call stored procedures in Spring Data JPA repositories. They are used in conjunction with the Spring Data JPA repository abstraction to provide a high-level, easy-to-use API for interacting with databases in Spring applications.
