Challenge page => https://overthewire.org/wargames/bandit/bandit6.html

This time the password is in a file which has a certain set of attributes. What makes this challenge unique is that the number of files you will have to sift through is huge.

Lets take a look at the contents of the `inhere` dir and one of its subdirs.


![Contents of inhere dir](https://dev-to-uploads.s3.amazonaws.com/i/uc0dlenhsis3pdxsbfka.png)

So, clearly we have our work cut out for us. Going through each one of the files will take a huge amount of time.

___

So how do we find the file which has the three attributes listed?

- human-readable
- 1033 bytes in size
- not executable

Hint 1: Once again, look at the man pages of the commands "you may need"
___


The hint was in the question itself :D

The `find` command comes in handy when searching for files with certain attributes. But we have to be careful with how we use it as it can search through the entire file system if needed.

Don't hesitate to fire up a few searches for the `find` command and see a few examples. Also, do gloss over the man page, as the flags will come in handy in the future as well.

Now that we've zeroed in on the `find` command, we need to ensure

- The search completes fast
- The search doesn't go through the entire filesystem, but just through the `inhere` dir
- It only outputs the name of the file that has the aforementioned attributes


___

Which are the flags of the `find` command that will help us narrow down the file that contains the password?

Hint 2: You don't need to ask Google or the Duck for this. Searching the man pages will suffice.
___


The man pages are quite handy aren't they? They are a bit verbose though. Then again that is how good documentation is supposed to be :)

So, we've figured out the flags required

- `-readable` for human-readable files
- `-size 1033c` for 1033 bytes
- `-executable` to ensure the find command filters for executable files

But wait, we need "non-executable" files. 

___
How do we negate the flag?

Hint 3: Usually man pages have a few examples also listed. Maybe our answer is there?
___

Jackpot! There is one example where the `-readable` file is negated.

![Flag negation example](https://dev-to-uploads.s3.amazonaws.com/i/k5775z2lv3ibhtjzv5f1.png)

Now we have everything we need. Assuming you are running the command from your home dir, the final command would be

`find ./inhere -readable -size 1033c \! -executable`

Let's try it.

![Solution](https://dev-to-uploads.s3.amazonaws.com/i/xefinz7nigmniwwszcex.png)

That was a pretty fast search. Onto the next challenge!