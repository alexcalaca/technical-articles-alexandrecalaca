# PostgresQL: PG::ConnectionBad: FATAL:  role "username" does not exist

Hey guys, how have you been?

Today, we are going to learn how to solve the following error message:

```ruby
PG::ConnectionBad: FATAL:  role "username" does not exist
```

### Introduction

The error message happens when you try to create a Rails database and the `role` is not found.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672542280559/14c59350-39ce-43c7-8352-6e9b1e32c054.png align="center")

In my example, `calaca` is the role.

#### **1 - Check if it's installed**

Just to make sure that `Postgresql` is already installed.

```ruby
which psql
```

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672512349051/a6ac651c-dc7c-4538-b2c8-028441d63358.png align="center")

---

#### 2 - Check the version

```ruby
psql --version
```

or

```ruby
psql --version
```

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672514130896/93846311-c6aa-40c9-9f82-5ddb69e26763.png align="center")

---

#### 3 - Start the PostgresQL service

```ruby
sudo service postgresql start
sudo service postgresql status
```

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672514497774/5ac81563-e17b-4f51-9893-25857160a320.png align="center")

---

#### 4 - Enter the PostgresQL terminal

```ruby
sudo -u postgres psql
```

You should be able to see something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672514635050/31723443-0d3d-4296-b3c3-10acd7e9a4c8.png align="center")

---

#### 5 - Create the role

In my example, `calaca` is my role.

```ruby
CREATE USER calaca SUPERUSER PASSWORD 'yourpassword';
```

---

#### 6 - Check if the new role is already available

```ruby
\du
```

You should be able to see something like this

![You](https://cdn.hashnode.com/res/hashnode/image/upload/v1672514992983/655cfb97-d053-4a3c-a471-be4526966f41.png align="center")

---

#### 7 - Create the databases

```ruby
CREATE DATABASE "database_name_development";
CREATE DATABASE "database_name_test";
```

---

#### 8 - Check if all databases have been created

```ruby
\l
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672538860259/313e4564-e877-4155-aa3b-d8d2a2f9a4fb.png align="center")

---

#### 9 - Set the role to own the databases

```ruby
ALTER DATABASE database_name_development OWNER TO username;
ALTER DATABASE database_name_test OWNER TO username;
```

In my example, `calaca` is my role.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672539856554/4580ac81-7b7a-4b1c-90f6-fa960c1cf766.png align="center")

The confirmation message is `ALTER DATABASE`.

---

#### 10 - Check if the databases belong to your role

```ruby
\l
```

#### You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672540102899/6dc3a5fe-9639-42ef-9390-02f66354b6de.png align="center")

---

#### 11 - Leave the terminal

```ruby
\q
```

You should see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672539111870/a23d85f8-e642-420d-8620-7d955fc4bad1.png align="center")

---

#### 12 - Create Rails databases

```ruby
rails db:create
```

You'll get a message that they already exist

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672540416567/5bb231bb-fc51-4b7a-8e04-3bdcf14cd632.png align="center")

---

#### 13 - Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467202120/39r84GZVW.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

### Conclusion

That's all for today. I hope this article helped you. Let me know if you have any questions.
