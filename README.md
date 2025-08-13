



**@SpringBootApplication** – A convenience annotation that combines
**@Configuration, @EnableAutoConfiguration, and @ComponentScan to bootstrap a Spring Boot application.
**- @Configuration: allows defining beans and settings
- @EnableAutoConfiguration: enables automatic configuration based on classpath
- @ComponentScan: automatically scans for components in this package and subpackages

**@Component** – Marks a class as a Spring‑managed bean so it is automatically detected & Instantiated during component scanning and registered in the application context.

// Bootstraps the Spring Application and returns the application 

ConfigurableApplicationContext run = SpringApplication.run(WishGeneratorApplication.class, args);

// Manually fetches the bean of type wishGenerator from the Spring context

wishGenerator wishG = run.getBean(wishGenerator.class);

**Controller → Service → Repository → Database**

**@Repository** – Handles direct database operations and data access logic. This layer maps to the database and performs CRUD operations.@Repository is typically applied to an **interface** rather than a class. This interface extends one of the Spring Data repository interfaces like JpaRepository, CrudRepository, or the base Repository interface.

**@Service** – Contains the business logic. It calls the repository layer to fetch or persist data and can include additional processing or transaction management.

**@Controller** – Manages incoming web requests, delegates processing to the service layer, and returns responses to the client.@Controller receives HTTP requests, calls the service methods, and returns responses.


**@Resource** is a Java EE standard annotation (from javax.annotation or jakarta.annotation) used for dependency injection.

@**Inject** annotation in Spring Boot is part of the JSR-330 standard (Java Dependency Injection specification) and is used to indicate a dependency injection point. It functions very similarly to Spring’s own @Autowired annotation but comes from the Java standard rather than being Spring-specific

The @**Autowired** annotation in Spring Boot is a key mechanism for automatic dependency injection. It tells the Spring framework to automatically find and inject the required beans (objects) into your class without you needing to manually instantiate or wire them
**Where Can You Use @Autowired?
****Constructor Injection** (recommended for required dependencies)

**Setter Injection** (for optional dependencies or to enable changing after construction)

**Field Injection** (injects directly into private fields, though less recommended)

@**Primary**: Use to designate a default bean for injection when multiple beans of the same type exist, so Spring injects it automatically unless specified otherwise.

@**Qualifier**: Use to explicitly specify which bean to inject when multiple beans of the same type are present, overriding the default or @Primary bean selection.
For example:     @Qualifier("bluedartCourier")


@**Bean** is a method-level annotation that tells Spring a method produces a bean to be managed in the Spring application context.

@**Order** defines the sorting priority of a bean or component, where a lower value means higher precedence during injection into collections or ordered processing.
    @Bean
    @Order(1)
    public CommandLineRunner commandLineRunner2() {

**CommandLineRunner** must be a Spring-managed bean to run on application startup
If you omit @Bean or don’t use @Component on the class, Spring won’t know about it, and the insertion logic inside won’t run.


