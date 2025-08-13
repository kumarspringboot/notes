/**
 * @SpringBootApplication is a shortcut for:
 *  - @Configuration: allows defining beans and settings
 *  - @EnableAutoConfiguration: enables automatic configuration based on classpath
 *  - @ComponentScan: automatically scans for components in this package and subpackages

 */

         // Bootstraps the Spring Application and returns the application context
        ConfigurableApplicationContext run = SpringApplication.run(WishGeneratorApplication.class, args);

        // Manually fetches the bean of type wishGenerator from the Spring context
        wishGenerator wishG = run.getBean(wishGenerator.class);


/**
 * @Component marks this class as a Spring-managed bean.
 * It will be detected and instantiated during component scanning.
 */
