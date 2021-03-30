## Externalized Configuration

1. Default properties (specified by setting SpringApplication.setDefaultProperties).

1. @PropertySource annotations on your @Configuration classes. Please note that such property sources are not added to the Environment until the application context is being refreshed. This is too late to configure certain properties such as logging.* and spring.main.* which are read before refresh begins.

1. Config data (such as application.properties files)

2. A RandomValuePropertySource that has properties only in random.*.

3. OS environment variables.

4. Java System properties (System.getProperties()).

5. JNDI attributes from java:comp/env.

6. ServletContext init parameters.

7. ServletConfig init parameters.

8. Properties from SPRING_APPLICATION_JSON (inline JSON embedded in an environment variable or system property).

9. Command line arguments.

10. properties attribute on your tests. Available on @SpringBootTest and the test annotations for testing a particular slice of your application.

11. @TestPropertySource annotations on your tests.

12. Devtools global settings properties in the $HOME/.config/spring-boot directory when devtools is active.

Config data files are considered in the following order:

1. Application properties packaged inside your jar (application.properties and YAML variants).

2. Profile-specific application properties packaged inside your jar (application-{profile}.properties and YAML variants).

3. Application properties outside of your packaged jar (application.properties and YAML variants).

4. Profile-specific application properties outside of your packaged jar (application-{profile}.properties and YAML variants).

## External Application Properties

1. The classpath root

2. The classpath /config package

3. The current directory

4. The /config subdirectory in the current directory

Immediate child directories of the /config subdirectory
