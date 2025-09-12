---
title: "Step-by-Step Guide to Forcefully Remove and Recreate Docker Containers"
datePublished: Fri Sep 12 2025 18:22:26 GMT+0000 (Coordinated Universal Time)
cuid: cmfh5zz0i000a02k16v5i6alb
slug: step-by-step-guide-to-forcefully-remove-and-recreate-docker-containers
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/kvxqWoJlMvs/upload/47bbfa7267e90f9cbc4d95e4879ae93a.jpeg
tags: docker, alexandrecalaca

---

# Steps

## Cleanup phase

This phase’s goal is to removes existing containers, volumes, networks and images

### Stop and remove volumes

`docker compose down --volumes --remove-orphans`

The previous command stops and removes containers, networks, and default volumes created by `docker compose up`.

* `--volumes`: also deletes named and anonymous volumes attached to the containers.
    
* `--remove-orphans`: removes any containers from earlier Compose runs that are not in the current `docker-compose.yml`.
    

---

### Remove any stopped containers

`docker compose rm -fsv`

The previous command explicitly removes any stopped containers from this project. This ensures no containers are left behind

* `-f`: force removal (no confirmation prompt).
    
* `-s`: stop the container if it’s running.
    
* `-v`: remove any anonymous volumes attached to these containers.
    

---

### Delete unused volumes

The following command deletes **all unused volumes** across the whole Docker host (not just our project), so, use it cautiously.

```plaintext
docker volume prune -f
```

`-f`: skips the confirmation prompt.  

Remember. Be careful: this can delete volumes from other projects if they’re not in use.

---

### Delete unused networks

The following command delete all unused networks across the Docker host.

```plaintext
docker network prune -f
```

`-f`: skips confirmation.

Again, safe unless you have manually created custom networks you still need.

---

### Delete dangling images

The following command deletes dangling images, which are images without a tag or not referenced by any container).

```plaintext
docker image prune -f
```

`-f`: skips confirmation.  

Only cleans dangling images, not all unused images. For a deeper clean, you’d need `docker image prune -af`.

---

## Rebuild phase

This phase forces a clean rebuild and restart.

### Rebuild images

The following command rebuilds all images defined in your Compose file.

```plaintext
 docker compose build --no-cache
```

* `--no-cache`: ignores Docker’s layer cache, forcing every instruction in the Dockerfile(s) to run again. It guarantees you’re building fresh images without reusing cached layers.
    

---

### Start the containers

The following command starts the containers in detached mode (`-d` = runs in the background). \`-d\` is optional.

```plaintext
docker compose up -d
```

Now, it’ll use the freshly rebuilt images. It’ll recreate networks and attaches containers as defined in the Compose file.

---

## Done

---