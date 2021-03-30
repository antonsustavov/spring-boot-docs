## Web Environment

A SpringApplication attempts to create the right type of ApplicationContext on your behalf. The algorithm used to determine a WebApplicationType is the following:

1. If Spring MVC is present, an **AnnotationConfigServletWebServerApplicationContext** is used

2. If Spring MVC is not present and Spring WebFlux is present, an **AnnotationConfigReactiveWebServerApplicationContext** is used

3. Otherwise, **AnnotationConfigApplicationContext** is used
