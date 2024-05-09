---
title: 'Linux Fundamentals: Explaining the ls command and beyond'
description: 'Explaining the different outputs of the ls commands, how to use them to understand concepts like file permissions, as well as how to use the built in terminal manual.'
canonicalUrl: "https://mohamedyamani.com/blog/linux-fundamentals-explaining-the-ls-command-and-beyond/"
pubDate: 2023-09-10
image: "/images/thumbnails/linux-fundamentals-explaining-the-ls-command-and-beyond.jpg"
imageAlt: "blue and white abstract painting"
---

If you ever used a Linux system before, chances are you're familiar with the `ls` command, or at least you know of it. Through understanding the output of this command, you can learn some fundamental concepts in Linux (or operating systems in general) like user management and file permissions. It's kinda fun, I promise.

For those of you that are not familiar with the `ls` command, I hope you can pick up at least this from the article...

## Golden nugget
If you ever find yourself unsure of what a command does, what argument does what, or the syntax of the command, always refer to the system's manual via the `man` command. You don't know what `ls` is? Screw Google. Enter `man ls` in your terminal. Not sure why someone would call a command that outputs text a `cat`? `man cat` (stands for concatenate).

Funnily enough, when I was first learning about this, I tried `man man` right off the bat. Boy was it lovely to see that it worked and indeed returned the manual description of the manual. Don't take my word for it though, try it yourself!

---

If you feel like sticking around a little bit more, I will try to explain the command for you.

*Note: you will encounter the word "directory" in this article, it's a fancier name for "folder" used in Unix/Unix-like contexts.*

## Level 0
The command `ls` lists the content of a directory, content like files and other directories. It is the equivalent to the graphical way of double clicking on a folder and seeing the icons of the different folders and files. 

So how come `ls` works even though we didn't provide a directory to list the content of? Well if you read the manual `man ls` you would know! Develop that reflex my friend, you will need it.

Entering `ls` without providing a directory will list the content of the current directory by default. What current directory you say?

Well the terminal is always pointing to a directory. By default when you open the terminal, it would be pointing at what's called the home directory, it is usually given the symbol `~` in the prompt which is just a shorthand of `/home/<your-username>/`. Don't take my word for it though, open up your terminal and enter `pwd` to check the current directory (use `man` to learn more about that command!).

## Level 1
Great. Now you can use the terminal to check the content of a directory. But now you're getting greedy, you want to extract more information -as you should-. Feel free to explore the arguments you can find in the manual! Some of the most common used ones would be:
- `ls -a` to view hidden items. Notice how the new items all have names starting with a `.`? That is how files are hidden in Linux/Unix. Neat right?
- `ls -l` to show more details about the listed items.

The last argument shows some cryptic output. That's our key to understanding more concepts!

## Level 2
The output of `ls -l` would look something like this. Let's try to depict it.
![Terminal output of the "ls -l" command](/images/ls-terminal-output.png)
You can notice that each item is on a separate line. Each line provides a piece of information about the item in a column, sort of like a table.

### Column 1: File type and permissions
The first character denotes the file type:
- `d` for directory.
- `-` for a regular file.
- `i` for a symbolic link (will not be covered in this article).

Notice how I said file type? Including directories? That's because in Linux, everything is a file. A directory is just a special kind of file. I might write an article about that someday! :)

The remaining part of the column indicates the file's permissions. It is divided into 3 parts. The left most part is the user owner's permission, the middle one is the group's permission and the right most part represents the world's (others') permission.
- `r` stands for read. It takes the first position.
- `w` stands for write. It takes the second position.
- `x` stands for execute. It takes the third permission.
- `-` indicates no permission depending on the position. If it's in the first one, it means the file does not have read permission. If it's in the second, it means no write permission, and so on.

I will assume that the notion of a user is familiar. However a *group* might be a new term.

A group is simply a collection of users. The introduction of such feature facilitates the administration of things like having the same permissions for a bunch of users.

Finally, *others*, or as some call it *world*, is anyone that is not the user owner or the group owner.

Notice also how many terms are being thrown here? And we're just getting started! That's what I meant by `ls` being a key to learning some fundamental concepts. Brace yourself!

### Column 2: Hard links count
Quite the confusing name right, it's in fact simple. A hard link is a copy of a file. The number indicates how many copies exist of that file in the file system.

### Column 3: User owner

### Column 4: Group owner

### Column 5: File size
In bytes. You can look up the manual on which argument to use to display the sizes in *human* readable format. On that note, search online how to properly search for keywords in the terminal manual.

### Column 6: Last modified date and time
The timestamp of when the file was last modified.

### Finally, column 7: the file name

## Level 3
You realize by now how much there's to know. You've asked yourself plenty of questions while reading the article. I sure did while writing it! But that's the beauty of it. Explore away your curiosity, discover what you can!

---

A lot of what has been briefly explained here could be developed into separate articles. I am planning on doing that someday in the near future :)

Hope you learned something!

---
 
Thumbnail picture by [Diane Picchiottino](https://unsplash.com/@diane_soko?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/blue-and-white-abstract-painting-Avy65GwRDUU?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
