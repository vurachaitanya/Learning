## Benthos Tool
- [Reff Doc](https://www.benthos.dev/docs/about)

For installing : `curl -Lsf https://sh.benthos.dev | bash`

- `benthos -help` - Help
- `benthos -list-processors|more` - Help in listing the documentation
- `benthos -print-yaml` - printing in Yaml format
- `benthos -print-json|jq '.'` - Print in Jsaon format
- `benthos -print-yaml --example kafka,jmespath,amqp` - It creates exaple combining kafka + Jmespath + AMQP config for you
- `benthos -C ./config.yaml` compile the configuration files
- `benthos list` - list the components which can be used by benthos
- `benthos -print-yaml --example file` shares the examples of file 


##### Sample CSV file :
- Generated from the command: `benthos -print-yaml --example csv`
```
http:
  address: 0.0.0.0:4195
  enabled: true
  read_timeout: 5s
  root_path: /benthos
  debug_endpoints: false
  cert_file: ""
  key_file: ""
input:
  type: csv
  csv:
    batch_count: 1
    #delimiter: ','
    parse_header_row: true
    paths: [sample.csv]
    
buffer:
  type: none
  none: {}
pipeline:
  processors: []
  threads: 1
output:
  type: stdout
  stdout:
    delimiter: ""
resources:
  caches: {}
  conditions: {}
  inputs: {}
  outputs: {}
  processors: {}
  rate_limits: {}
logger:
  add_timestamp: true
  format: json
  json_format: true
  level: INFO
  prefix: benthos
  static_fields:
    '@service': benthos
metrics:
  type: http_server
  http_server:
    path_mapping: ""
    prefix: benthos
tracer:
  type: none
  none: {}

```

### Sample Output :
```
{"Age":"41","Height (in)":"74","Name":"Alex","Sex":"M","Weight (lbs)":"170"}
{"Age":"42","Height (in)":"68","Name":"Bert","Sex":"M","Weight (lbs)":"166"}
{"Age":"32","Height (in)":"70","Name":"Carl","Sex":"M","Weight (lbs)":"155"}
{"Age":"39","Height (in)":"72","Name":"Dave","Sex":"M","Weight (lbs)":"167"}
{"Age":"30","Height (in)":"66","Name":"Elly","Sex":"F","Weight (lbs)":"124"}
{"Age":"33","Height (in)":"66","Name":"Fran","Sex":"F","Weight (lbs)":"115"}
{"Age":"26","Height (in)":"64","Name":"Gwen","Sex":"F","Weight (lbs)":"121"}
{"Age":"30","Height (in)":"71","Name":"Hank","Sex":"M","Weight (lbs)":"158"}
{"Age":"53","Height (in)":"72","Name":"Ivan","Sex":"M","Weight (lbs)":"175"}
{"Age":"32","Height (in)":"69","Name":"Jake","Sex":"M","Weight (lbs)":"143"}
{"Age":"47","Height (in)":"69","Name":"Kate","Sex":"F","Weight (lbs)":"139"}
{"Age":"34","Height (in)":"72","Name":"Luke","Sex":"M","Weight (lbs)":"163"}
{"Age":"23","Height (in)":"62","Name":"Myra","Sex":"F","Weight (lbs)":"98"}
{"Age":"36","Height (in)":"75","Name":"Neil","Sex":"M","Weight (lbs)":"160"}
{"Age":"38","Height (in)":"70","Name":"Omar","Sex":"M","Weight (lbs)":"145"}
{"Age":"31","Height (in)":"67","Name":"Page","Sex":"F","Weight (lbs)":"135"}
{"Age":"29","Height (in)":"71","Name":"Quin","Sex":"M","Weight (lbs)":"176"}
{"Age":"28","Height (in)":"65","Name":"Ruth","Sex":"F","Weight (lbs)":"131"}
{"@timestamp":"2021-03-17T22:44:54+05:30","@service":"benthos","component":"benthos","level":"INFO","message":"Pipeline has terminated. Shutting down the service."}
```
