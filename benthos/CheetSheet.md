## Benthos Tool

For installing : `curl -Lsf https://sh.benthos.dev | bash`

- `benthos -help` - Help
- `benthos -list-processors|more` - Help in listing the documentation
- `benthos -print-yaml` - printing in Yaml format
- `benthos -print-json|jq '.'` - Print in Jsaon format
- `benthos -print-yaml --example kafka,jmespath,amqp` - It creates exaple combining kafka + Jmespath + AMQP config for you
- `benthos -C ./config.yaml` compile the configuration files
- `benthos list` - list the components which can be used by benthos
- `benthos -print-yaml --example file` shares the examples of file 
