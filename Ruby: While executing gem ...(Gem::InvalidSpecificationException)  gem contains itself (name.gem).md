# Ruby: While executing gem ...(Gem::InvalidSpecificationException)  gem contains itself (name.gem)

Hey guys, how's it going?

Today, we are going to learn how to fix the error Gem::InvalidSpecificationException) gem contains itself (name.gem)

`gem::InvalidSpecificationException) gem contains itself (name.gem), check your file list`

#### Introduction

As software developers and human beings, one vital skill is to be able to understand and solve problems.

Failure happens everywhere and every time, we already expect that, the difference is how people approach and face problems.

In software development, one important characteristic is to be able to grasp the error message. Identify solutions for problems must be our motto.

#### 1 - What

What's the error message? The error message says:

```ruby
ERROR:  While executing gem ... (Gem::InvalidSpecificationException)
    gem-1.12.22 contains itself (gem_name-1.12.22.gem), check your files list
```

An example

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671723368263/5Xi25KzTH.png align="center")

#### 2 - When

When does it happen? The error happens when you run `gem build gem_name.gemspec.`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671721936983/JHMT84Pju.png align="center")

#### 3 - Why

Why does it happen? It happens because the ruby gem calls git to find out what files to include or check in your gem.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671721936983/JHMT84Pju.png align="center")

In the previous example, since there's already a rulers-1.12.22.gem in git, there's going to be a conflict with the previous and the new file.

That's why the error message says: \`rulers-1.12.22 *contains itself*\`

#### 4 - How

How does it happen? This behavior is because of the following part of the gemspec file:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671723873149/G8N9RDacl.png align="center")

Ruby gems always list the gem's repo situation: \`git ls-files -z\`

Try it and see the result

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671724101951/ObpZ8M4n7.png align="center")

#### 5 - Solution

The solution is to remove the gem file, locally and remotely, done.

```ruby
rm gem_name-1.1.1.gem
git commit -am "fix: Remove gem_name-1.1.1.gem"
git push
```

#### 6 - Test

Run `gem build gem_name.gemspec`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671724909798/-OIoejCGB.png align="center")

#### 7 - Celebrate

![The Office' Turns 15: Celebrate With the 15 Best Episodes to Watch While  You're Stuck Inside](https://www.cheatsheet.com/wp-content/uploads/2020/03/the-office-niagara.jpg align="left")

#### Conclusion

That\`s all for today. I hope this article helped you. Let me know if you have any questions.
