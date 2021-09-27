# Blackbox exporter configuration with query  

Use query param modify the module
```
/probe?target=target.com:3000&module=http_2xx
/probe?target=target.com:3000&module=http_2xx&HTTP.Method=GET&HTTP.headers.my_field=TKeel
/probe?target=target.com:3000&module=http_2xx&HTTP.Method=GET&HTTP.fail_if_ssl=true
/probe?target=target.com:3000&module=http_2xx&HTTP.valid_status_codes.0=200&HTTP.valid_status_codes.1=201&HTTP.valid_status_codes.2=204
```

### <http_probe> with Query
```yml

  # Accepted status codes for this probe. 
  HTTP.valid_status_codes.0=<int>&HTTP.valid_status_codes.1=<int>&...

  # Accepted HTTP versions for this probe.
  HTTP.valid_http_versions=<string>&...

  # The HTTP method the probe will use.
  HTTP.method=<string>&...

  # The HTTP headers set for the probe.
  HTTP.headers.<string>=<string>&...
  
  # Probe fails if response body matches regex.
  HTTP.fail_if_body_matches_regexp=<regex>&...

  # Probe fails if response body does not match regex.
  HTTP.fail_if_body_not_matches_regexp=<regex>&...
  
  # Probe fails if response header matches regex. For headers with multiple values, fails if *at least one* matches.
  HTTP.http_header_match_spec.0=<http_header_match_spec>&HTTP.http_header_match_spec.1=<http_header_match_spec>&...


  # Probe fails if response header does not match regex. For headers with multiple values, fails if *none* match.
  HTTP.fail_if_header_not_matches.0=<http_header_match_spec>&HTTP.fail_if_header_not_matches.1=<http_header_match_spec>&...
    
  # The HTTP basic authentication credentials for the targets.
  HTTP.basic_auth.username=<string>&HTTP.basic_auth.password=<secret>&...

  # The bearer token for the targets.
  HTTP.bearer_token=<secret>&...
  
  # The body of the HTTP request used in probe.
  HTTP.body=<string>&...
