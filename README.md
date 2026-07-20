# scope.yaml

Engagement scope for sonnycroco. Read-only.

```yaml
target:
  name:    Nikos Pitsilis
  handle:  sonnycroco
  origin:  Greece
  role:    Security Researcher

approach:
  language: python            
  deps:     none              
  outputs:  [tools, writeups]

in_scope:

  published tools:
    - id:      h1grep
      summary: grep for disclosed HackerOne reports from the terminal
      filters: [keyword, severity, cwe, program, votes, bounty]
      edge:    reverse-engineered GraphQL — encodes crash-avoidance rules
               for query shapes H1's endpoint rejects
      install: pip install h1grep
      socket:  https://socket.dev/pypi/package/h1grep

    - id:      nuclei-index
      summary: map a CVE id to local nuclei-templates, emit the exact
               rate-limited nuclei command
      traits:  [indexes-once, cached, "--json", "stdlib-only", "py>=3.9"]
      install: pip install nuclei-index
      socket:  https://socket.dev/pypi/package/nuclei-index

  writeups:
    - box:   HTB Reactor
      chain: CVE-2025-55182 -> shell -> exposed Node.js debugger -> root
    - box:   HTB MonitorsFour
      chain: PHP type-juggling -> leaked hashes -> admin -> Cacti RCE in Docker -> exposed Docker API -> Windows host

  adjacent:
    # cloud surface the tooling gets pointed at
    - aws-ssm-secure-parameter-retrieval
    - S3-filesize-checker

out_of_scope:
  - anything not public on github.com/sonnycroco
```

<a href="https://pypi.org/project/h1grep/">h1grep</a> <a href="https://socket.dev/pypi/package/h1grep"><img align="middle" alt="Socket" src="https://badge.socket.dev/pypi/package/h1grep/0.1.0?artifact_id=tar-gz"></a> <a href="https://pepy.tech/projects/h1grep"><img align="middle" alt="PyPI Downloads" src="https://static.pepy.tech/personalized-badge/h1grep?period=total&units=INTERNATIONAL_SYSTEM&left_color=BLACK&right_color=GREEN&left_text=downloads"></a> &nbsp;&nbsp;&nbsp; <a href="https://pypi.org/project/nuclei-index/">nuclei-index</a> <a href="https://socket.dev/pypi/package/nuclei-index"><img align="middle" alt="Socket" src="https://badge.socket.dev/pypi/package/nuclei-index/0.1.0?artifact_id=tar-gz"></a> <a href="https://pepy.tech/projects/nuclei-index"><img align="middle" alt="PyPI Downloads" src="https://static.pepy.tech/personalized-badge/nuclei-index?period=total&units=INTERNATIONAL_SYSTEM&left_color=BLACK&right_color=GREEN&left_text=downloads"></a> &nbsp;&nbsp;·&nbsp;&nbsp; <a href="https://www.linkedin.com/in/nikos-pitsilis/" align="middle">linkedin</a> &nbsp;·&nbsp; <a href="https://app.hackthebox.com/public/users/3376923" align="middle">hackthebox</a>
