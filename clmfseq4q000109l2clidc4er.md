---
title: "permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock"
datePublished: Tue Sep 12 2023 04:02:46 GMT+0000 (Coordinated Universal Time)
cuid: clmfseq4q000109l2clidc4er
slug: permission-denied-while-trying-to-connect-to-the-docker-daemon-socket-at-unixvarrundockersock
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694462609927/5b3ddc52-6add-4d06-9dee-9e5b52181836.png
tags: ubuntu, docker, ruby, ruby-on-rails, debian

---

---

## Full error message

```apache
docker-compose up db
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json?all=1&filters=%7B%22label%22%3A%7B%22com.docker.compose.config-hash%22%3Atrue%2C%22com.docker.compose.project%3Dvrs-backend%22%3Atrue%7D%7D": dial unix /var/run/docker.sock: connect: permission denied
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694457722048/ed8f3c03-579e-4e46-924d-2538c81c05c2.png align="center")

---

## Brief explanation

The error message we're seeing indicates that the user running the `docker-compose` command does not have the necessary permissions to connect to the Docker daemon, which manages Docker containers.

This typically happens because the user doesn't have the required privileges to interact with Docker.

---

## Context

You are developing a Ruby on Rails web application and want to containerize it using Docker for easier development and deployment. Your application relies on a database, and you plan to use a separate Docker container for the database service.

In my case, I tried using one docker container in a Ruby on Rails application.

---

## Current configuration

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694462962621/3dd1ed03-ae30-4770-a547-8bead61cb936.png align="center")

---

## Check your user

```apache
whoami
```

or

```apache
echo $USER
```

---

## **Add User to the Docker Group**

```apache
sudo usermod -aG docker $USER
```

Replace `$USER` with your actual username.

Since my username is `calaca`. Take a look at the result:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694459872392/eed4e86f-6dfe-404b-a287-b14cd5da0b35.png align="center")

---

## Add user to docker group

```apache
sudo usermod -aG docker $USER
```

Replace `$USER` with your actual username.

Since my username is `calaca`. Take a look at the result:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694460449341/8dbd80b7-304c-418c-8725-dabbee9b51e3.png align="center")

---

## Check group membership

```apache
groups $USER
```

Replace `$USER` with your actual username.

Since my username is `calaca`. Take a look at the result:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694459940174/e031f86b-c4e2-434b-9b2a-067457b4df4c.png align="center")

---

## Restart docker

```apache
sudo systemctl restart docker
```

---

## Check docker socket permission

```apache
ls -l /var/run/docker.sock
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694458346003/0e9fe9be-07c6-4bd9-8350-f45bac3ae25f.png align="center")

---

## Restart the Docker service again

```apache
sudo systemctl restart docker
```

---

## Restart the OS

---

## Run the test

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694462471636/2c1a8ab4-d102-48cb-964e-9e177f34d194.png align="center")

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article has been helpful to you. Please feel free to reach out if you have any questions. Your thoughts, suggestions, and corrections are more than welcome.

By the way, don't hesitate to drop your suggestions for new blog articles.

I look forward to seeing you next time.

---