---
title: Docker cheatsheet
date created:  2024-08-16T16:43 
date modified: 2024-08-16T16:43 
tags:
- software
- docker
---

## Execute docker compose file

```bash 
docker-compose -f docker-compose-dev.yaml up -d --build
```
>[!note] `-d` means the execution is detached, `--build` means it will build the containers

## connect to the logs of another docker

```bash
    docker logs <container-name> -f
```

>[!note] `-f` makes the command follow the logs, keeping it opened regardless of what you say
