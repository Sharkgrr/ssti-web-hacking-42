# How to Prevent Template Injections Attack

## Enconding 

One of the most effective ways to prevent attacks is by using the "Encoding" method, which is based on validating and sanitizing the characters entered into inputs and outputs. This involves transforming all data input into text. For example, converting `__main__` to `main` or `.global()` to `global` aims to neutralize any malicious scripts.

## Whitelisting 
Whitelists are effective for blocking attack attempts with invalid values. To implement this, simply create a list of allowed protocols, and the application will apply the rule to determine whether a request should be permitted.


Referências
* https://evernow.com.br/como-proteger-sua-empresa-de-ataques-xss-e-assegurar-seus-dados/
* https://portswigger.net/web-security/cross-site-scripting/preventing
