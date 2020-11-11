# saturday-night-action
Just a dockerfile and a script hanging out on a Saturday night. 

# Dockerfile

```
FROM ubuntu
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
```

# Entry Point Script, entrypoint.sh

```
#!/bin/bash
echo "This is my custom action! :D"
```

# Workflow, main.yml

```
name: Saturday Night
on: push
jobs:
  main:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: managedkaos/saturday-night-action@main
```
