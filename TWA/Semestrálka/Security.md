- Provider
	- ORM entity user provider
- Login
	- Form - `php bin/console make:security:form-login`
			-!!!NOT PROTECTED AGAINST CSRF
	- API - `php bin/console make:controller --no-template ApiLogin`
		- Login here to generate API token for authenticating the API calls
		- 
	- [Rate limiter](https://symfony.com/doc/current/security.html#limiting-login-attempts)
- Twig template access checking
```
{% if is_granted('ROLE_ADMIN') %}
    <a href="...">Delete</a>
{% endif %}
```
