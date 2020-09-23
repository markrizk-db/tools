## What is this?

I built a simple docker-compose file that sets up an Ubuntu VM with `k8s`, `kind`, and `python` installed.

## How to use?
```
$ docker-compose up --build -d
...
$ docker exec -it docker_vm_1 /bin/bash
```