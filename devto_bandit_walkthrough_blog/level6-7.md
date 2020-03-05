Challenge page => https://overthewire.org/wargames/bandit/bandit7.html

> The password for the next level is stored somewhere on the server and has all of the following properties:

>    owned by user bandit7
>    owned by group bandit6
>    33 bytes in size


This challenge is very similar to the last one, the only difference being that we will have to search the entire filesystem.

We already know from the [last challenge](https://dev.to/kkaosninja/overthewire-bandit-level-5-level-6-walk-through-50cf) that using the `find` command is the best way to go about this.

___

Once again, what flags of the `find` command are required to search for this file?

*Hint 1*: Searching the man page will be enough to get the flags required
___


Alright then. After searching the man page, we have found the flags.

- `-user bandit7`
- `-group bandit6`
- `-size 33c`

Since the file is "somewhere on the server", we will have to run the search from the root `/` directory.

So the final command would be

`find / -user bandit7 -group bandit6 -size 33c`

Let's execute it then

![find command initial output](https://dev-to-uploads.s3.amazonaws.com/i/lrikbyiwcknl5s6i7b1h.png)

___
Be warned, since the user we used to log in is not `root`, the `find` command will visit a lot of directories which the `bandit6` user does not the permissions to read. So we will encounter a lot of errors.

How do we get the errors out of the way so that we get a "clean" result?

*Hint 2*: A few web searches should yield a result. Read up on streams and I/O redirection
___

If you couldn't figure that out, its ok!

An easy way to get the errors out of the way is to send them to `/dev/null` as follows.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/jfw3h9g940wy0c3wkxp7.png)

Looks like we got it!

What I did there was redirect the "stderr" stream to `/dev/null`, basically discarding it, and therefore ensuring that it does not get printed on the terminal.

Couple of articles to understand this better

- [What Are stdin, stdout, and stderr on Linux?](https://www.howtogeek.com/435903/what-are-stdin-stdout-and-stderr-on-linux/)

- [An Introduction to Linux I/O Redirection](https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-i-o-redirection)

- [What Is /dev/null in Linux?](https://www.maketecheasier.com/dev-null-in-linux/)

Being comfortable with I/O redirection is an important part of being comfortable with the command line. Don't be afraid to get your hands dirty.

Note: A lot of programs will send useful error info to `stderr` in case of failure. So when debugging, and especially if there are a ton of error messages, it is common practice to redirect `stderr` to a file so that you can go through it later to figure out what happened.

Onto the next challenge!