---
title: 'Linux Fundamentals: File Permissions and Ownership'
description: 'Explaining Linux fundamental concepts: file permissions, ownership and the chmod command to change the permissions of a file in the two different syntaxes, octal and symbolic.'
canonicalUrl: 'https://mohamedyamani.com/blog/linux-fundamentals-file-permissions-and-ownership/'
pubDate: 2023-09-19
image: "/images/thumbnails/linux-fundamentals-file-permissions-and-ownership.jpg"
imageAlt: "a window with rain drops on the glass"
---

In my last article [Explaining the ls command and beyond](https://mohamedyamani.com/blog/linux-fundamentals-explaining-the-ls-command-and-beyond/), I broke down the `ls` command, how to interpret the output, and introduced some command line concepts. It was quite the jargon, and to some of you, it was unfamiliar.

As such, I'll dedicate some articles (like this one) to explain that very jargon, or at least make it a bit less unfamiliar to you.

---

Linux is a multi-user system, and it does not mean what you think it does (or at least what I did).

A multi-user system is not just a system that allows having multiple users, but one that can also be used by many users at the same time. The keyword here is **at the same time**.

You might ask yourself, how can a computer be used at the same time by different people? Well, a computer does not require you to sit in front of it to use it. You can remotely access it for example using the program _Remote Desktop Connection_ if you're using Windows. Or using SSH to access the system via the command line. That way, multiple users can work on the same machine, using the same resources.

Try to picture that scenario of multiple user accessing a computer, it's a mess. What's stopping user B from playing around with user A's work? As a person that likes to troll, I would say, nothing. The options are endless, and it stops being fun when you're user A.

It seems that this trolling concern existed in the 70's too. Unix was built with the design of a multi-user architecture; it introduced file ownership and permissions. And Linux naturally inherited this design as well.

## Unix multi-user system design

### Ownership

Every file in the system belongs to a user and to a group. This is called ownership, and it enables the system to make the distinction between these 3 cases:

- A user that owns the file.
- A user that belongs to the group that owns the file.
- A user that is neither of the above. Which is called _other_ or _world_ as I've explained in the last article.

### Permissions

Permissions are _who gets to do what_ with a file. The who part is determined by ownership, it is one of the 3 cases I mentioned above.

Now to the fun part, _do what_. What can be done to a file? The answer is found in the first column in the output of `ls -l`:

- Read.
- Write.
- Execute.

These 3 permissions hold different meanings for files and directories. It's one of the things that I found troubling to understand when I was first learning Linux.

#### Permissions of a file

- Read: the file's content can be read. By using `cat` or opening it with a text editor for example.
- Write: the file's content can be changed.
- Execute: the file can be considered a program and executed. If you ever downloaded an [AppImage](https://appimage.org) before, you're likely to have encountered the error `Permission denied`. The reason was because the file did not have the execute permission.

#### Permissions of a directory

- Read: the directory's content can be read, you can `ls` the directory, but you cannot open it graphically by double clicking, I'll explain that in a bit.
- Write: the directory's content can be changed, meaning you can create/delete/rename/move files and directories within it.
- Execute: you can enter the directory, meaning `cd` into it. This permission alone is not enough to open the directory graphically too.

So what's up with directories graphically? Well, nothing. Just think about it for a second.

What happens exactly when you double click on a directory? Sounds like a stupid question right? I'll let you be the judge of that.

A window pops up, **showing** the content of that directory. But another thing happens as well, we **enter** that directory.

Ultimately, opening a directory graphically makes use of two permissions:

- Read permission: because the window lists the content of the directory.
- Execute permission: because we entering the directory.

Don't take my word for it though, I might be saying nonsense after all. Open your terminal, and play around with files/directories with different permissions.

## Chmoding playground

What better way is there to understand than seeing what you're learning in action, right?

In order to see the effect of the different permissions, you'll need to be able to change them. That's where the `chmod` command comes into the picture. I'll briefly introduce it, refer to `man` for more details.

The `chmod` command supports two syntaxes:

- Octal (I won't cover what octal is, or why the syntax was named after it)
- Symbolic

Remember how a user can be either an owning user, a user that belongs to the owning group or neither? Well each of those gets a permission.

### Octal

The syntax is straightforward:

`chmod <XXX> file`

Where XXX is a 3 digit number. Reading from left to right:

- 1st digit: permission for the owning user.
- 2nd digit: permission for the owning group
- 3rd digit: permission for others (also called world, anyone that is neither of the above).

Each permission is "represented" by a number:

- Read: 4
- Write: 2
- Execute: 1

To describe a permission as a digit, add the numbers of the permissions you wish to include. For example, the permission of a file that is readable and writable would be described with the number 6. Which is 4 (read permission) + 2 (write permission).

Repeat the same process for the each digit to represent the file's permission for every kind of user.

Say you want your file to be readable and writable for you (the owner), and only readable for anyone else:

`chmod 600 someFile.txt`

The first digit representing your permission. The second and third digits representing respectively the owner group and others' permissions, which is 0, none.

You change your mind, you open your heart and want to share the file with others, but without having to worry about trolls (like myself). Instead of giving no permission to the group owner and others', you give them read access instead.

`chmod 644 someFile.txt`

You get the idea.

### Symbolic

This one is a bit tricky. You use these symbols to represent permissions:

- `u` meaning user owner.
- `g` meaning group owner.
- `o` meaning others.
- `r` for read permission.
- `w` for write permission.
- `x` for execute permission.

Let's start simple.

`chmod +x someFile.txt`

This adds the execute permission for everyone. The user owner, the group owner, and others.

`chmod -x someFile.txt`

Removes the execute permission for everyone.

`chmod +rw someFile.txt`

Adds the read and write permissions for everyone. So far so good, I hope.

Now it gets, compositional let's say.

`chmod u=rwx someFile.txt`

Assigns read, write and execute permissions to the user owner.

`chmod go=r someFile.txt`

Assigns the read permission to the group owner as well as to others.

Etc.

---

I hope you learned something :)

Keep the trolls away.

---
  
Thumbnail picture by [Jr Kopa](https://unsplash.com/@jrkorpa?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/a-window-with-rain-drops-on-the-glass-E2i7Hftb_rI?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
