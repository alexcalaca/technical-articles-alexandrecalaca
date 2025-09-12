---
title: "A Complete Guide to Uninstalling Docker completely on Pop!_OS and Ubuntu-based Systems"
datePublished: Fri Sep 12 2025 17:47:55 GMT+0000 (Coordinated Universal Time)
cuid: cmfh4rlcc000202l84rel3zuz
slug: a-complete-guide-to-uninstalling-docker-completely-on-popos-and-ubuntu-based-systems
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/06y6wukkSKg/upload/10f64b1222531d9f0c2d6dadff5ca974.jpeg
tags: ubuntu, linux, docker, popos, alexandrecalaca

---

## Steps

### Stop the service

It’s not mandatory, but before uninstalling, it's a good practice to stop any running Docker services.

```plaintext
sudo systemctl stop docker
```

---

### Remove docker packages

It’s used to **completely and forcefully remove** a list of specified packages from a Debian-based Linux system like Pop!\_OS. All the following packages are docker related.

In short, this command aims to leave no trace of the specified Docker packages, which is an essential step for a complete and thorough uninstallation.

```plaintext
sudo apt-get purge -y docker-engine docker docker.io docker-ce docker-ce-cli containerd runc
```

and also

```plaintext
sudo apt-get purge -y docker-compose-plugin
```

---

### Clean up leftover files

In summary, the command is a non-interactive, forced, and recursive deletion of all major Docker-related data and configuration directories. This is an essential step for a complete uninstallation.

```plaintext
sudo rm -rf /var/lib/docker/ /var/lib/containerd/ /etc/docker ~/.docker/
```

---

### Remove docker group

When you install Docker, it creates a `docker` group. This group is created for security and convenience, allowing users to run Docker commands without needing `sudo` every time.

In this case, since we don’t need it anymore, we’re going to delete the `docker` group.

```plaintext
 sudo groupdel docker
```

---

### Remove docker repository entry

By deleting this file, you are essentially telling your system to stop looking for Docker updates from the official Docker repository. This is an important step in a complete uninstallation, as it ensures that apt-get update no longer tries to connect to a repository for a program that you no longer want on your system.

```plaintext
sudo rm /etc/apt/sources.list.d/docker.list
```

---

### Remove dependencies

**In summary, the goal is to remove old, useless downloaded package files** to free up disk space, but it does not remove any installed software.

It is a maintenance command that is good to run periodically after uninstalling software or upgrading your system.

```plaintext
sudo apt-get autoremove -y --purge docker-ce docker-ce-cli
sudo apt-get autoclean
```

---

### Verify the installation

```plaintext
docker --version
docker compose --version
docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1757690473776/66a9c5f4-1d96-4f3d-9701-d1006e480bb8.png align="center")

---