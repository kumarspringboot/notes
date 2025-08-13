



@SpringBootApplication – A convenience annotation that combines
@Configuration, @EnableAutoConfiguration, and @ComponentScan to bootstrap a Spring Boot application.
- @Configuration: allows defining beans and settings
- @EnableAutoConfiguration: enables automatic configuration based on classpath
- @ComponentScan: automatically scans for components in this package and subpackages

@Component – Marks a class as a Spring‑managed bean so it is automatically detected & Instantiated during component scanning and registered in the application context.

// Bootstraps the Spring Application and returns the application 

ConfigurableApplicationContext run = SpringApplication.run(WishGeneratorApplication.class, args);

// Manually fetches the bean of type wishGenerator from the Spring context

wishGenerator wishG = run.getBean(wishGenerator.class);

Controller → Service → Repository → Database

@Repository – Handles direct database operations and data access logic. This layer maps to the database and performs CRUD operations.

@Service – Contains the business logic. It calls the repository layer to fetch or persist data and can include additional processing or transaction management.

@Controller – Manages incoming web requests, delegates processing to the service layer, and returns responses to the client.@Controller receives HTTP requests, calls the service methods, and returns responses.




