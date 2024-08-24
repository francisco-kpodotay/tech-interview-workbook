# Advanced Java

## Spring and Spring Boot

* What is Spring Framework and what are its core features?

    - The Spring Framework (Spring) is an open source software development framework that provides infrastructure support for building primarily Java-based applications

    - Spring helps developers create high-performing applications using plain old Java objects (POJOs)
    - Spring is a low-cost and flexible framework that improves coding efficiency and reduces overall application development time through efficient use of system resources

    - Spring removes configuration work so that developers can focus on writing business logic
    - Spring handles the infrastructure so developers can focus on the application

    - Core features: - Spring IoC (responsible for the dependencies and configurations of individual components)
                     - Spring MVC (MVC is one of the most commonly used application patterns in which the program code is divided into three main parts)

                     - Spring AOP (Aspect Oriented Programming)
                     - Spring Data JDBC
                     - Spring Web Flow (allows developers to implement web application flows)
                     - Spring Security (allows developers to create complex authentication and authorization mechanisms designed for projects of various sizes)

                     - Spring Test

* Explain the main differences between Spring and Spring Boot.

    - Spring is a framework and Spring Boot is a extension for Spring that helps developers configure and uses utilities that automate Spring configuration

    - Spring provides a Dependency Injection feature, while Spring Boot provides autoconfiguration
    - Spring doesn’t provide any server for testing, while Spring Boot provides embedded servers (Tomcat and Jetty)
    - Spring needs a lot of a boilerplate code, while Spring Boot doesn’t require a lot of boilerplate code
    - Spring doesn’t provide an in-memory database, while Spring Boot provides several in-memory databases
    - Spring doesn’t provide automation tools for defining dependencies, while Spring Boot handles the dependencies automatically
    
* How does Spring Boot simplify the configuration of Spring applications?

    - Spring boot is simplifies Dependency management and the configuration of a web app
    - Spring Boot Starters are a set of pre-configured templates that automatically manage dependencies for your application
    - Including a specific starter all the required dependencies and versions are correctly managed


    - Spring Boot uses application.properties or application.yml files to store and manage application configuration
    - Located in the src/main/resources directory
    - Spring Boot framework automatically reads and applies these settings when the application starts

    - You can bind your custom configuration properties to java object with the @ConfigurationProperties annotation
    - Allows you to directly map configuration settings to Java classes and fields

          @ConfigurationProperties(prefix = "+36")   
    e.g.: class PhoneNumber{
            private final String phoneNumber;

            public PhoneNumber(String phoneNumber){
                this.phoneNumber = phoneNumber;
            }
          }

    - You can inject your custom configuration into other classes

    - It provides easy ways to configure your applications through annotations and also with xml files
    - There are a lot of different annotations that you can use for all kind of problems
    - Also it will automatically builds the application

    - It provides implementations for important parts of the code like a server (Tomcat), logger(Slf4j), json parser (Jackson)
    - Spring boot also provides you other frameworks like security, web application With easy integration



* What is a dependency injection (DI) and how does Spring support it?   <-------Issues possibly here>

    - Dependency injection is a programming technique that makes a class independent of its dependencies
    - It achieves that by decoupling the usage of an object from its creation
    - Helps you to follow SOLID’s dependency inversion and single responsibility principles
    - You can introduce interfaces to break the dependencies between higher and lower level classes
    - If you do that, both classes depend on the interface and no longer on each other
    - Improves the reusability, limits the ripple effect if you need to change lower level classes

    - If you need to change lower level classes
    - The Spring container “injects” objects into other objects or “dependencies”
    - Allows for loose coupling of components and moves the responsibility of managing components onto the container

    - Inversion of Control is a principle in software engineering which transfers the control of objects or portions of a program to a container or framework
    - IoC enables a framework to take control of the flow of a program and make calls to our custom code

    - Spring implements an IoC
    - ApplicationContext interface represents the IoC container
    - The Spring container is responsible for instantiating, configuring and assembling objects known as beans, as well as managing their life cycles
    - Spring framework provides several implementations of the ApplicationContext(AnnotationConfigApplicationContext, ClassPathXmlApplicationContext)
    - To assemble beans, the container uses configuration metadata (Annotations, XML)
    - ApplicationContext scans classes for the @Bean annotations, then initializes and manages the beans defined in these classes


    - Dependency-Injection types: - Constructor-Based Dependency Injection
                                  - Setter-Based Dependency Injection
                                  - Field-Based Dependency Injection


* How can you define a bean in Spring? Provide examples.

    - A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container


    - You can configura a spring bean through XML configuration file

    e.g.:   <?xml version="1.0" encoding="UTF-8"?>
            <beans xmlns="http://www.springframework.org/schema/beans"
                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                xsi:schemaLocation="http://www.springframework.org/schema/beans
                https://www.springframework.org/schema/beans/spring-beans.xsd">
            
                <bean id="studentAmiya" class="Student">
            
                </bean>
            
            </beans>


    - Using @Component annotation: - Annotations are a form of metadata that provides data about a program
                                   - Provide supplemental information about a program
                                   - @Component is an annotation that allows Spring to automatically detect the custom beans
                                   - In spring there are specific versions of the @Component annotation like: @Service, @Repository


    e.g.:   @Component("collageBean")
            public class College {
                public void test()
                {
                    System.out.println("Test College Method");
                }
            }

            @Service
            public class StudentService{
                public void service(){
                    System.out.println("This is a service");
                }
            }


            @Repository
            public class RoomRepository{
                public List<Room> getRooms(){
                    //Implementation
                }
            }


    - Using @Bean annotation: - One of the most important annotation
                              - It is applied on a method to specify that it returns a bean to be managed by Spring context
                              - Bean annotation is usually declared in Configuration classes methods


    e.g.:       @Configuration
                public class CollageConfiguration{
                    @Bean
                    public Collage collageBean(){
                        return new Collage();
                    }

                }


* What is inversion of control (IoC) and how is it implemented in Spring?

    - Inversion of Control is a principle in software engineering
    - It transfers the control of objects or portions of a program to a container
    - IoC enables to take control of the flow and make calls to our custom code

    - The interface ApplicationContext represents the IoC container
    - The Spring container is responsible for instantiating, configuring and assembling objects known as beans, as well as managing their life cycles.

    - Spring provides several implementations of the ApplicationContext interface: - AnnotationConfigApplicationContext
                                                                                   - ClassPathXmlApplicationContext
                                                                                   - FileSystemXmlApplicationContext
                                                                                   - WebApplicationContext

    - (In most usecases we use the AnnotationConfigApplicationContext)
                                                                        


* What is a RESTful API, and how can you develop a Web API using Spring Boot?

    API:
    - An API is a set of definitions and protocols for building and integrating application software
    - Sometimes referred to as a contract between an information provider and an information user
    - If you want to interact with a computer or system to retrieve information or perform a function, an API helps you communicate what you want to that system so it can understand and fulfill the request

    - It used to share resources and information while maintaining security, control, and authentication


    REST:
    - REST is a set of architectural constraints (not a protocol or a standard)
    - A client request is a transfer, a representation of the state of the resource to the requester
    - This information delivered via HTTP (JSON, HTML, XML or plain text) (JSON is the most popular)
    - Headers and parameters are also important in the HTTP methods
    - They contain important identifier information as to the request's metadata, authorization, uniform resource identifier (URI), caching, cookies
    - There are request headers and response headers (each with their own HTTP connection information and status codes)

    - Criterias: - Client-server architecture, requests managed through HTTP
                 - Stateless client-server communication (no client information is stored between get requests, each request is separated)
                 - Cacheable data that streamlines client-server interactions
                 - Uniform interface between components: - resources requested are identifiable
                                                         - resources can be manipulated by the client
                                                         - self-descriptive messages returned to the client
                                                         - hypertext/hypermedia is available

                 - A layered system that organizes each type of server
                 - Code-on-demand (optional)

    - https://www.redhat.com/en/topics/api/what-is-a-rest-api


    - You can develop Web API's in spring by using the Spring Web MVC framework
    - It has configurations and annotations to create web apis





* How do you handle HTTP requests in Spring MVC? Give an example.

    - You can handle http request by a class that has the @RestController annotation
    - It has annotations for get, put, delete and post methods too


    e.g.:

    @RestController
    public class WeatherController{

        @GetMapping("/api/weather")
        public ResponseEntry<?> getWeather(){
            //implementation
        }

        @PutMapping("/api/weather/{id}")
        public ResponseEntry<?> updateWeather(@PathVariable int id){
            //implementation
        }

        @PostMapping("/api/weather/")
        public ResponseEntry<?> saveWeather(){
            //implementation
        }

        @DeleteMapping("/api/weather/{id}")
        public ResponseEntry<?> deleteWeather(@PathVariable int id){
            //implementation
        }
    }

## Entity Relationships, ORM, Spring Data

* What is ORM (Object Relational Mapping)? What are the benefits, when to use?

    - Object Relational Mapping is a technique used in creating a "bridge" between object-oriented programs and relational databases
    - Lets you query and manipulate data from a database using an object-oriented paradigm
    - ORM library is a library written in your language of choice
    - Encapsulates the code needed to manipulate the data, so you don't use SQL anymore, you interact with an object
    

    - Benefits: - It speeds up development time
                - Decreases the cost of development
                - Handles the logic required to interact with databases
                - Improves security (eliminate SQL injection attacks)
                - You write less code


    - Disadvantages: - ORMs are generally slower than SQL
                     - Hard to learn
                     - You have to set it up
    

    - When to use it: - When interacting with a database using OOP languages
                      - When you have to perform CRUD operations



* What is JPA?

    - Java Persistence API is a specification of Java
    - It is used to persist data between Java object and relational database
    - It is a Java specification that provides a programming interface for managing relational data in Java applications
    - JPA is designed to simplify database access and reduce the amount of repetitive and boilerplate code required to interact with relational databases

    - With JPA, developers can define entity classes that map to database tables, specifying the relationships between entities, as well as the attributes and constraints of each entity

    - JPA acts as a bridge between object-oriented domain models and relational database systems
    - JPA is just a specification, it doesn't perform any operation by itself (abstraction)
    - It requires an implementation
    - ORM tools like Hibernate, TopLink and iBatis implements JPA specifications for data persistence


* What is the difference between JPA and Spring Data JPA?

    - Spring Data JPA is yet another layer of abstraction over the JPA
    - It provides a higher-level abstraction over JPA by reducing boilerplate code and providing ready-to-use functionalities
    - Simplifies the development of data access layers in Java applications
    - Defined interfaces provide the services that the framework handles using JPA to serve the results
    - Spring Data JPA integrates with JPA implementations like Hibernate to offer database persistence capabilities

    - Features: - Automatic CRUD operations
                - Query generation from method names
                - Pagination support


* What is the difference between Hibernate ORM and Spring Data JPA?

    - Hibernate is an object-relational mapping solution for Java environments
    - Hibernate provides a reference implementation of the Java Persistence API (ORM tool)

    - Spring Data repository abstraction is to significantly reduce the amount of boilerplate code required to implement data access layers for various persistence stores
    - Spring Data JPA is not a JPA provider
    - Adds an extra layer of abstraction on the top of our JPA provider
    

    - Hibernate is a JPA implementation, while Spring Data JPA is a JPA Data Access Abstraction
    - Spring Data offers a solution to GenericDao custom implementations
    - Spring Data can also generate JPA queries through method name conventions
    - Spring Data JPA is not an implementation or JPA provider (it's just an abstraction used to significantly reduce the amount of boilerplate code required to implement data access layers for various persistence stores)



* How can you configure database connection properties in a Spring Boot application?

    - You can configure database connection through the application.properties file in the resources package/folder

    e.g.: 

        spring.jpa.hibernate.ddl-auto=update                <=== can be none, update, create, or create-drop
        spring.datasource.url=jdbc:postgresql://localhost:5432/weatherforecastapi
        spring.datasource.username=postgres
        spring.datasource.password=admin
        spring.datasource.driver-class-name=org.postgresql.Driver
        spring.jpa.show-sql=true


            none: No change is made to the database structure.

            update: Hibernate changes the database according to the given entity structures.

            create: Creates the database every time but does not drop it on close.

            create-drop: Creates the database and drops it when SessionFactory closes.




* Explain the concept of cardinality in entity relationships. How does it impact the design and mapping of entities?


    - We can configure a relationship as either one way(Unidirectional) or two ways(Bidirectional)
    - In a unidirectional relationship, only one entity has a relationship field or property that refers to the other
    - In a bidirectional relationship, each entity has a relationship field or property that refers to the other entity

    Relationship types between tables:

    - One To One: - A entity is onli linked to one entity of the other entity and vise veras 


            Example:
                  - A relation between User & Role table
                  - One User will have only one Role

                  - Unidirectional: - We can create unidirectional one to one relation by applying @OneToOne on the relational field at any side

                  - Bidirectional: - In order to satisfy the bidirectional relationship, we need to apply @OneToOne on both the sides
                  - We need to have mappedBy attribute into any side to tell that the mapping is already done by other side and don’t create additional column




    - One To Many: - Relationship between two entities A and B in which an element of A may be linked to many elements of B, but a member of B is linked to only one element of A

            Example: 
                - Maintain a relation of one to many between User & Role table
                - To satisfy One to Many relationship One user will have multiple roles

                - Unidirectional: - By applying @OneToMany on the relational field at any side
                                  - We want to have a one to many relationship from User to Role, we need to add a field with type List<Role> in the User entity (one user will have many roles)

                                  - We need to apply @OneToMany on the field with a type List<Role> in the User entity



                - Bidirectional: - We need to apply @OneToMany at one sides
                                 - And @ManyToOne at other side also

                                 - @OneToMany at field with type List<Role> in User entity
                                 - @ManyToOne at on the field with type User in the Role entity
                                 - We need to have mappedBy attribute in @OneToMany


    - Many To One: - Multiple entities are associated with exactly one other entity
                   - Multiple records in a table can be associated with exactly one record in another table


            Example: 
                - We have to maintain a relation between User & Role table
                - Multiple Users will have only one Role

                - Unidirectional: - a unidirectional relationship between User & Role entities by applying @ManyToOne on the relational     field at any side

                                  - We need to add a field with type Role in the User entity (many users will have one role)
                                  - We need to apply @ManyToOne on the field with a type Role in the User entity


                - Bidirectional: - We need to apply @ManyToOne at one sides and @OneToMany at other side also
                                 
                                 - @ManyToOne at on the field with type Role in User entity
                                 - @OneToMany at on the field with type List<User> in the Role entity
                                 - We need to have mappedBy attribute in @OneToMany


    - Many To Many: - Relationship between two entities
                    - Multiple records in a table are associated with multiple records in another table


            Example: - A relation of many to many between User & Role table
                     - Multiple Users will have multiple roles


                     - Unidirectional: - User & Role entities by applying @ManyToMany on the relational field at any side
                                       - We need to add a field with type List<Role> in the User entity (means many users will have many roles)

                                       - We need to apply @ManyToMany on the field with a type List<Role> in the User entity



                     - Bidirectional: - Apply @ManyToMany at both the sides
                                      - And @ManyToMany at other side also

                                      - @ManyToMany at on the field with type List<Role> in User entity
                                      - @ManyToMany at on the field with type List<User> in the Role entity

                                      - we need to have mappedBy attribute in any side

    
* How to create a custom repository in Spring Data JPA?

    - First you have to create a custom repository interface with the implementation of the custom method
    - Than you need to extend the interface with CrudRepository or JpaRepository
    - The CrudRepository is containing the basic crud operations (findAll, findById, save, saveAll, etc...)
    - The JpaRepository extends the CrudRepository and also have some special features for streaming and paginations
    - The repository infrastructure tries to autodetect custom implementation fragments


    e.g.:   interface UserRepository extends CrudRepository<User, Long>{
                User findByFirstName(String firstName);
            }

            interface UserRepository extends JpaRepository<User, Long>{
                User findByFirstName(String firstName);
            }


    - Jpa will automatically creats an implementation for this interface at runtime
    - It will do it by the naming conventions
    - When you try to name the method Inteliij will automaticalli show the naming conventions


* What is the difference between FetchType.Eager and FetchType.Lazy?

    - Fetch Type represents the strategy for fetching data from the database

    - FetchType.LAZY: - Indicates that the data should be fetched lazily when it called for the first time
                      - Retrieves parent entity data first then retrieves child entity data on demand only

    - FetchType.EAGER: - Indicates that the data should be fetched eagerly when it called for the first time
                       - Retrieves parent & child entity data together at a time


        - Full explanation: https://javatechonline.com/entity-relationship-in-jpa-hibernate-orm/#What_is_Lazy_Eager_Loading


## Spring Security

* What are some essential features of Spring Security?

    - Spring Security is built using the Spring framework in Java
    - Aims to make it easy for developers to secure web applications against common exploits (Cross-Site Request Forgery)
    - Its major function is to manage authentication and authorization at both the Web request and method invocation levels
    - Core concepts: - Authentication (Is the user really who he claims to be?)
                     - Authorization (Does the user have the appropriate role?)
                     - Password Storage (How is the password stored? In Memory or a database.)
                     - Servlet Filters (Are there any new filters that we need to add or just use the default ones provided by the spring team?)



* How can you secure a Spring Boot application using Spring Security?

    - We configured the filter chain to establish the order and configuration of security filters (specifying authentication and authorization rules)   --> WebSecurityConfig  class

    - Created an authentication manager and authentication provider using a custom UserDetailsService implementation (which loads user-specific data during authentication)     --> AuthTokenFilter, UserDetailsServiceImpl

    - A utility class was implemented to handle JWT tokens, providing methods for token generation, extraction, and verification  --> JwtUtils

    - Implemented a filter to support JWT authentication, intercepting requests, validating tokens, and setting user authentication if the token is valid   --> AuthTokenFilter

    - An authentication error handler class was created to handle authentication failures and customize error responses     -->AuthEntryPointJwt 

    
* Explain how the security filter chain works.

    - We have filters inside the web application which we use to define any pre logic work before actual business logic executes
    - In between my client and actual servlets, we can use filters
    - Filters are responsible to intercept each and every request of the web application
    - They execute what logic we have defined inside these filters
    - The HTTP request going to pass through it and the response also pass through the filters based on the way that it is going

    - Spring Security Filters: - filters intercept each request & work together to identify if Authentication is required or not
                               
    - Authentication: - Filters like UsernamePasswordAuthenticationFilter will extract username/ password from HTTP request & prepare Authentication type object
                      
    - AuthenticationManager: - It's responsibility to to manage all the authentication providers available

    - AuthenticationProvider: - AuthenticationProviders has all the core logic of validating user details for authentication

    - UserDetailsService: - It helps in retrieving, creating, updating, deleting the User Details from the DB/storage systems.

    - PasswordEncoder: - Service interface that helps in encoding & hashing passwords.

    - SecurityContext: - Once the request has been authenticated, the Authentication will usually be stored in a thread-local SecurityContext managed by the SecurityContextHolder
                       - Helps during the upcoming requests from the same use



    - SecurityFilterChain: - You have a sequence of filters
                           - Each filter doing some handling and afterward giving to the following object (filter)
                           - Each object has a security filter object behind which gets called after the filter has played out its own handling
                           - It is invalid as the chain worth or it realizes on its own that it is the final remaining one in the sequence

                           - All filters are chained in the order of their definition
                           
                           - Core components: - Security Filter Chain: - Is a sequence of filters that Spring Security applies to each incoming HTTP request
                                              - Security Filter Chain Configuration: - You define the security filter chain in your Spring Security configuration class
                                              - Security Filters: - These are individual filters that perform specific security tasks.


            !!!!!!!!!!!!!!!!!!!!!!This is in the securityConfig file!!!!!!!!!!!!!!!!!!!!!


        - Core security filters: - Authentication Filter: - Responsible for handling user authentication
                                 - Authorization Filter: - Enforces access control policies and checks whether a user is authorized to access a resource
                                 - Exception Handling Filter: - Manages exceptions and handles security-related errors
                                 - CSRF (Cross-Site Request Forgery) Filter: - Protects against CSRF attacks
                                 - Session Management Filter: - Manages user sessions and their associated security contexts


* What is JWT (JSON Web Token), and how can you use it for authentication?

    - Is an open standard
    - Defines a compact and self-contained way for securely transmitting information between parties as a JSON object
    - This information can be verified and trusted because it is digitally signed
    - JWTs can be signed using a secret (with the HMAC algorithm)
    

    - Authorization: - This is the most common scenario for using JWT
                     - Each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token
                     

    - Information Exchange: - JSON Web Tokens are a good way of securely transmitting information between parties
                            - Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are
    
    - Authentication: - For authentication in spring security with jwt first the user sends a request with the username and password
                      - Than it goes through the security filterchains where it AuthenticationManager will delegate an authentication provider
                      - The authentication provider will check if the credentials are good or not
                      - If the credentials are incorrect it lets to the other filter
                      - Finally the last filter catches if the previous filters didn't caught the incorrect credentials
                      
                      - If the credentials were correct we can generate a jwt token for the user
                      - It will be generated from the user's name and the jwt secret and it has a timestamp
                      - After that we can create a JwtResponseDTO that we can sand back to the client

                      - After each request now we don't need to check if the username and password exists we only need to check the jwt
                      - Does the request has a jwt?
                      - Does the jwt signed?
                      - Does the jwt expired?



* Explain the concept of authentication and authorization in Spring Security.

    - Authentication: - Is a process that verifies that someone or something is who they say they are
                      - Typically use some form of authentication to secure access to an application or its data
                      
                      e.g.: - You usually have to enter your username and password
                            - Behind the scenes, it compares the username and password you entered with a record it has on its database
                            - If the information you submitted matches, the system assumes you are a valid user and grants you access
                            - The purpose of authentication is to verify that someone or something is who or what they claim to be



    - Authorization: - Authorization is the security process that determines a user or service's level of access
                     - We use authorization to give users or services permission to access some data or perform a particular action
                     - The most common authorization is Role based authorization
                     - Each user has a role
                     - Each role has different, in some cases same permission

                     - Different roles have accesses to different resources
                     - It depends on the Role's permissions

    - Authentication verifies the identity of a user or service before granting them access
    - Authorization determines what they can do once they have access

* How can you implement method-level security using annotations in Spring?

    - In spring there are a bunch of annotations to achive method level security:
        - @Secured annotation: is used to specify a list of roles on a method e.g: @Secured({ "ROLE_VIEWER", "ROLE_EDITOR" })

        - @PreAuthorize annotation checks the given expression before entering the method e.g: @PreAuthorize("hasRole('ROLE_VIEWER')")
                                                                                               @PreAuthorize("hasRole('ROLE_VIEWER') or hasRole('ROLE_EDITOR')")


        - @PostAuthorize annotation verifies it after the execution of the method and could alter the result e.g: @PostAuthorize("#username == authentication.principal.username")

        - @PreFilter annotation to filter a collection argument before executing the method e.g: @PreFilter("filterObject != authentication.principal.username")
        

## Integration testing

* What is integration testing, and how does it differ from unit testing?

    - Integration testing is a type of software testing where components of the software are gradually integrated and then tested as a unified group
    - These components are already working well individually
    - With integration testing, testers want to find defects that surface due to code conflicts between software modules when they are integrated with each other

    - Conflicts between software modules happen for many reasons: - incompatibility between subsystem versions
                                                                  - data format conflict
                                                                  - different processing logic

    - Integration testing pinpoints those communication issues between software components
    - It occurs after unit testing and before system testing

    - Unit tests: - Unit tests focus on a single part of a whole application in total isolation (usually, a single class or function)
                  - These tests should be free of side effects, you will want to run them directly without involving any other system
                  - Ideally, this includes no dependencies
                  - Dependencies can be swapped out to allow for testing in isolation (Mocking)


    - Integration tests: - Is to test how parts of the application work together as a whole
                         - Integration testing considers side effects
                         - Integration test could use the connection to a database to query and mutate the database
                         - Often “mocks away” these external resources the way mocking is used in unit tests
                         - Integration testing helps find issues that are not obvious by examining the application’s or a specific unit’s implementation
                         - Integration testing discovers defects in the interplay of several application parts.


                         - An integration test is that it deals with multiple parts of your application
                         - While unit tests always take results from a single unit, such as a function call
                         - Integration tests may aggregate results from various parts and sources


* How can you configure and set up integration tests in a Spring Boot project?

    - We have to import spring-boot-starter-test into our dependecies
    - The H2 DB eliminates the need for configuring and starting an actual database for test purposes

    - Integration tests focus on integrating different layers of the application
    - No mocking is involved
    - Ideally, we should keep the integration tests separated from the unit tests and should not run along with the unit tests
    - We can do this by using a different profile to only run the integration tests or you simply can use a inmemory database


        @SpringBootTest(
        webEnvironment = SpringBootTest.WebEnvironment.MOCK,
        classes = Application.class)
        @AutoConfigureMockMvc
        @TestPropertySource(
        locations = "classpath:application-integrationtest.properties")
        public class EmployeeRestControllerIntegrationTest {

            @Autowired
            private MockMvc mvc;

            @Autowired
            private EmployeeRepository repository;

            // write test cases here
        }


    - @SpringBootTest annotation is useful when we need to bootstrap the entire container
    - Use the webEnvironment attribute of @SpringBootTest to configure our runtime environment (WebEnvironment.MOCK here so that the container will operate in a mock servlet environment)
    - @TestPropertySource annotation helps configure the locations of properties files specific to our tests

    - Application-integrationtest.properties contains the details to configure the persistence storage

        spring.datasource.url = jdbc:h2:mem:test
        spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.H2Dialect

    (   NOT AS IMPORTANT!!!!!!!!!!!!
    - If want to avoid bootstrapping the real application context but use a special test configuration we can use @TestConfiguration annotation
    - We can create a separate test configuration class

        @TestConfiguration
        public class EmployeeServiceImplTestContextConfiguration {
            
            @Bean
            public EmployeeService employeeService() {
                return new EmployeeService() { 
                    // implement methods 
                };
            }
        }


    - Classes annotated with @TestConfiguration are excluded from component scanning, we need to import it explicitly in every test where we want to @Autowire it
    @Import annotation
    )


    - To test the Service layer, we don’t need to know about how the persistence layer is implemented
    - We can use the mocking support


        @MockBean
        private EmployeeRepository employeeRepository;

    - It creates a Mock for the EmployeeRepository, which can be used to bypass the call to the actual EmployeeRepository

        @Before
        public void setUp() {
            Employee alex = new Employee("alex");

            Mockito.when(employeeRepository.findByName(alex.getName()))
            .thenReturn(alex);
        }


    - @RunWith(SpringRunner.class) provides a bridge between Spring Boot test features and JUnit
    - This annotation will be required


    - @DataJpaTest provides some standard setup needed for testing the persistence layer
            - Configuring H2, an in-memory database
            - Setting Hibernate, Spring Data, and the DataSource
            - pPerforming an @EntityScan
            - Turning on SQL logging

    - To carry out DB operations, we need some records already in our database
    - We can use TestEntityManager
    - The Spring Boot TestEntityManager is an alternative to the standard JPA EntityManager that provides methods commonly used when writing tests


    - To test the Controllers, we can use @WebMvcTest
    - It will auto-configure the Spring MVC infrastructure for our unit tests
    - @WebMvcTest will be limited to bootstrap a single controller
    - We can also use it along with @MockBean to provide mock implementations for any required dependencies
    - @WebMvcTest also auto-configures MockMvc, which offers a powerful way of easy testing MVC controllers without starting a full HTTP server.
    

    - Testing controller: 

        @Test
        public void givenEmployees_whenGetEmployees_thenReturnJsonArray() throws Exception {
            
            Employee alex = new Employee("alex");

            List<Employee> allEmployees = Arrays.asList(alex);

            given(service.getAllEmployees()).willReturn(allEmployees);

            mvc.perform(get("/api/employees")
            .contentType(MediaType.APPLICATION_JSON))
            .andExpect(status().isOk())
            .andExpect(jsonPath("$", hasSize(1)))
            .andExpect(jsonPath("$[0].name", is(alex.getName())));
        }

* How do you perform an HTTP request in an integration test for a Spring Boot application?

    - In spring boot test we have a TestRestTemplate class, which is a mock resttemplate
    - With this class you can make http request like in a normal application
    - You just have to autowire the field
    - With this approach you start the full server with all of it's endpoints

    e.g.: 

    @SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
    class HttpRequestTest {

        @LocalServerPort
        private int port;

        @Autowired
        private TestRestTemplate restTemplate;

        @Test
        void greetingShouldReturnDefaultMessage() throws Exception {
            assertThat(this.restTemplate.getForObject("http://localhost:" + port + "/",
                    String.class)).contains("Hello, World");
        }
    }


    - Another approach is to only start the layer where Spring handles the incoming HTTP request and hands it off to your controller
    - It will still process the http request, but without the cost of starting the server
    - To achive this you can use MockMvc 
    - You have to use the @AutoConfigureMockMvc
    

    e.g.: 

    @SpringBootTest
    @AutoConfigureMockMvc
    class TestingWebApplicationTest {

        @Autowired
        private MockMvc mockMvc;

        @Test
        void shouldReturnDefaultMessage() throws Exception {
            this.mockMvc.perform(get("/")).andDo(print()).andExpect(status().isOk())
                    .andExpect(content().string(containsString("Hello, World")));
        }
    }


* How can you mock dependencies or external services in Spring Boot integration tests?

    - To mock dependencies wecan use the @MockBean annotation from the spring boot test framework library
    - This will automatically generate a mock for the class that we want to use it on
    - You can use the mockito's when().thenReturn() methods to tell the mock what should it return when a specific function is getting called

    e.g.:


    @WebMvcTest(GreetingController.class)
    class WebMockTest {

        @Autowired
        private MockMvc mockMvc;

        @MockBean
        private GreetingService service;

        @Test
        void greetingShouldReturnMessageFromService() throws Exception {
            when(service.greet()).thenReturn("Hello, Mock");
            this.mockMvc.perform(get("/greeting")).andDo(print()).andExpect(status().isOk())
                    .andExpect(content().string(containsString("Hello, Mock")));
        }
    }

* How do you configure an embedded H2 database for integration testing in Spring Boot?

## DevOps

* What is CI/CD (Continuous Integration/Continuous Deployment), and what are its benefits?

    - CI/CD automates much or all of the manual human intervention traditionally needed to get new code from a commit into production, encompassing the build, test (including integration tests, unit tests, and regression tests), and deploy phases, as well as infrastructure provisioning

    - With a CI/CD pipeline, development teams can make changes to code that are then automatically tested and pushed out for delivery and deployment
    - CI/CD is an essential part of DevOps and any modern software development practice

    - Benefits: - Downtime is minimized and code releases happen faster
                - Maximize development time
                - Improving an organization's productivity
                - Increasing efficiency
                - Streamlining workflows through built-in automation, testing, and collaboration
                - Decrease development complexity

                
* What is Docker and Docker Compose?

    Docker: 
        - An open platform for developing, shipping, and running applications
        - Docker enables you to separate your applications from your infrastructure so you can deliver software quickly
        - You can manage your infrastructure in the same ways you manage your applications
        - You can significantly reduce the delay between writing code and running it in production

        - Docker provides the ability to package and run an application in a loosely isolated environment called a container
        - The isolation and security lets you run many containers simultaneously on a given host
        - Containers are lightweight and contain everything needed to run the application, so you don't need to rely on what's installed on the host
        - You can share containers while you work, and be sure that everyone you share with gets the same container that works in the same way
        - The Docker engine only runs on the Linux operating system


    Docker-compose:
        - Docker Compose is a tool for defining and running multi-container applications
        - It is the key to unlocking a streamlined and efficient development and deployment experience
        - Simplifies the control of your entire application stack, making it easy to manage services, networks, and volumes in a YAML configuration file
        - With a single command, you create and start all the services from your configuration file


            `docker-compose up` <-- start the docker containers
            `docker-compose down` <-- stops the docker containers

        - Works in all environments; production, staging, development, testing, as well as CI workflows



* Explain the difference between an image and a container in Docker.

    - You can use Docker containers to package software in containers and run them on target machines
    - Docker containers run on any machine or virtual machine where the Docker engine is installed
    - They run without knowledge of the underlying system architecture
    - A Docker container is a container made using the Docker containerization platform

    **IMPORTANT**
    - A Docker container is a runtime environment with all the necessary components—like code, dependencies, and libraries—needed to run the application code without using host machine dependencies
    - Container runtime runs on the engine on a server, machine, or cloud instance


    - Docker images are read-only templates that contain instructions for creating a container
    - A Docker image is a snapshot or blueprint of the libraries and dependencies required inside a container for an application to run


* What is a Dockerfile?

    - Dockerfile is essentially the build instructions to build the image
    - The advantage of a Dockerfile is that the automatic builds will ensure you have the latest version available
    
    - Dockerfiles are text files that list instructions for the Docker daemon to follow when building a container image
    - When you execute the docker build command, the lines in your Dockerfile are processed sequentially to assemble your image
    - Instructions are keywords that apply a specific action to your image (such as copying a file from your working directory, or executing a command within the image)
    - Instructions are usually written in uppercase


    e.g.: 
            FROM eclipse-temurin:21-jre-alpine
            WORKDIR /tmp
            COPY target/*.jar app.jar
            ENTRYPOINT ["java","-jar","app.jar"]



* How can you set up a basic CI/CD pipeline for a Spring Boot application?

    - You can set up a simple CI/CD pipeline in Github Actions
    - There are a lot of templates where you can choose from
    - For java spring applications you can choose the maven.yml template
