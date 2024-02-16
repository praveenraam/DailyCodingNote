#### It is a tool provided by pivotal Web service  , with this we can easily start an SB project 

### Modules
- **initializr-actuator:** It provides additional information and statistics on project generation. It is an optional module.
- **initializr - bom:** In this module, **BOM** stands for **Bill Of Materials**. In Spring Boot, BOM is a special kind of **POM** that is used to control the **versions** of a project's **dependencies**. It provides a central place to define and update those versions. It provides flexibility to add a dependency in our module without worrying about the versions.  
- required to create products. It explains **what, how,** and **where** to collect required materials.
- **initializr-docs:** It provides documentation.
- **initializr-generator:** It is a core project generation library.
- **initializr-generator-spring:**
- **initializr-generator-test:** It provides a test infrastructure for project generation.
- **initializr-metadata:** It provides metadata infrastructure for various aspects of the projects.
- **initializr-service-example:** It provides custom instances.
- **initializr-version-resolver:** It is an optional module to extract version numbers from an arbitrary POM.
- **initializr-web:** It provides web endpoints for third party clients.


### Use Custom Web UI [http://start.spring.io](http://start.spring.io/)

![[Pasted image 20240214141122.png]]

- **Project** is the Package Manager - Maven is our choice
- **SpringBoot** is the version - Go with the latest version
- **Project Meta Data** :
	- Group is the name of the Package
	- Artifact is the name of the Application
	- Description is for the description part 
	- Package can be either Jar or War
	- Java version is to go with latest
- **Dependencies** - choose the required and click on download

### Hello World 
- Once you 