# Docker

Lint Dockerfile

```bash
# Install
sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.17.5/hadolint-Linux-x86_64
sudo chmod +x /bin/hadolint
# Lint
hadolint Dockerfile
```

Fix:

```bash
Need to get 14.1 MB of archives.
After this operation, 340 kB of additional disk space will be used.
E: You don't have enough free space in /var/cache/apt/archives/.
The command '/bin/sh -c apt-get install -y postgresql-contrib-11 postgresql-plpython-11' returned a non-zero code: 100
Failed to build container
```

with

```bash
docker container prune; docker rmi $(docker images -q); docker rm -v $(docker ps -qa)
```
