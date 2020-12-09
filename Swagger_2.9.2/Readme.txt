<!-- maven dependencies -->

<dependency>
	<groupId>io.springfox</groupId>
	<artifactId>springfox-swagger-ui</artifactId>
	<version>2.9.2</version>
</dependency>
<dependency>
	<groupId>io.springfox</groupId>
	<artifactId>springfox-swagger2</artifactId>
	<version>2.9.2</version>
</dependency>

Swagger URLs to exclude from security check

/v2/api-docs, /configuration/ui, /swagger-resources/**, /configuration/security, /swagger-ui.html, /webjars/**,/api/**


We can add below code in WebSecurityConfigurerAdapter impl class

@Override
public void configure(WebSecurity web) throws Exception {
	web.ignoring().antMatchers(excludedUrl);
}