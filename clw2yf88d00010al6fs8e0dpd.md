---
title: "How to run Rails migrations within a docker environment"
datePublished: Sun May 12 2024 03:07:10 GMT+0000 (Coordinated Universal Time)
cuid: clw2yf88d00010al6fs8e0dpd
slug: how-to-run-rails-migrations-within-a-docker-environment
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jOqJbvo1P9g/upload/a3ac940f69d31801bc3bce85183084cf.jpeg
tags: docker, ruby, ruby-on-rails, alexandrecalaca

---

---

## **Docker**

Docker is a popular platform for containerization that offers several benefits for developers, system administrators, and DevOps teams. Here are some of the key benefits of using Docker:

* **Portability**:  
    Docker containers encapsulate an application and its dependencies, making it easy to move the application across different environments—whether it's development, testing, or production. This ensures consistency and reduces the "it works on my machine" problem.
    
* **Isolation**:  
    Docker containers provide process and file system isolation. Each container runs independently of the host system and other containers, making it easier to manage dependencies and preventing conflicts between applications.
    
* **Simplified Dependency Management:**  
    Docker containers package an application and its dependencies into a single unit. This simplifies dependency management, as developers don't need to worry about installing and configuring dependencies on different machines.
    

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

## App running

Make sure your app is up and running.

---

## Identify the app's name

```ruby
docker ps
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703039643846/1c4f8c2e-c28d-40d0-bf18-6b146e133c05.png?auto=compress,format&format=webp align="left")

---

### Brief explanation

The `docker ps` command is used to list the currently running Docker containers on your system. Specifically, it shows information about containers that are in the "Up" state, meaning they are currently active and running.

Here's a breakdown of the command:

* `docker`: This is the command-line interface for interacting with Docker.
    
* `ps`: This stands for "process status" and is a common command on Unix-like operating systems to display information about active processes.
    

When you run `docker ps`, you'll typically see a table of information about the running containers. The output includes details such as:

1. **Container ID:** A unique identifier for the container.
    
2. **Image:** The Docker image from which the container was created.
    
3. **Command:** The command that was used to start the container.
    
4. **Created:** The time elapsed since the container was created.
    
5. **Status:** Indicates whether the container is currently running or stopped.
    
6. **Ports:** Information about ports mapped from the container to the host system.
    
7. **Names:** The name assigned to the container.
    

If you want to see information about all containers, including those that are stopped, you can use the `docker ps -a` command. This will show a list of all containers, regardless of their current state.

**COPY**

**COPY**

```ruby
docker ps -a
```

Understanding the status and details of running containers is useful for managing and troubleshooting Dockerized applications.

---

## Docker exec

`docker exec` is a command used in Docker to execute commands in a running container. It allows you to run a command inside a specified container that is already running.

Basic syntax:

```ruby
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

Step-by-step, let's build our final command. So far, we know we need the container name and the `docker exec` command.

---

## Interact with the container

```ruby
docker exec -it my_app_1 /bin/bash
```

You should be able to see something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703560227814/78935947-7c11-492f-8747-fea7009afa38.png?auto=compress,format&format=webp align="left")

`-i (or --interactive)`: This option allows you to keep STDIN open even if not attached. It provides an interactive shell session, enabling you to send input to the container.

`-t (or --tty)`: This option allocates a pseudo-TTY, or terminal. It allows you to interact with the container in a way that simulates a real terminal, making it suitable for running interactive commands.

Although `/bin/bash` is not going to be part of our last command, its usage helps us in checking our progress along the way. The command to start an interactive Bash shell inside the container.

---

## Run the migration

```ruby
sudo docker exec -it my_app_1 bundle exec rails db:migrate
```

---

## **Done**

---

### Conclusion

By following these steps, you can easily run Rails migrations within a Docker container without the need to modify Docker configurations.

This approach ensures consistent testing environments across different machines and simplifies the testing process for developers working with your Rails application.

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---