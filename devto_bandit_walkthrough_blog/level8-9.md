Challenge page => https://overthewire.org/wargames/bandit/bandit9.html

*Level Goal*
> The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

*Commands you may need to solve this level*

> grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

This challenge is similar to the last one as well, as it involves searching for the password in a file that already contains a huge amount of text, making manual searching impractical.

Let's take a look at the file in question shall we?

![file contents](https://dev-to-uploads.s3.amazonaws.com/i/tivx5gm6000u6hembrt2.png)

Normally this is where I would put the *Hint 1* part. But if you've been reading the previous walk-throughs and trying to solve this on your own, Google or DuckDuckGo should have been your first goto step. So its a pretty obvious hint.

Do not hesitate to use the search engines! Its not possible for one person to know everything. Besides, this is a learning process. You will naturally remember the commands after enough practice.


So, after some web searches, we can safely narrow down the commands required to `sort` and `uniq`

`sort` well, sorts the text files in alphabetical order. 

`uniq` (from the DESCRIPTION section in its man file) 

> Filter adjacent matching lines from INPUT (or standard input), writing to OUTPUT (or standard output).
> With no options, matching lines are merged to the first occurrence.

So `uniq` cannot work on its own, as it needs a file with identical lines adjacent to each other, which will only happen if the file was sorted beforehand.

So we will need to pipe the output of sort to uniq to get the unique lines. Let's try it out shall we?

![unique lines of data.txt](https://dev-to-uploads.s3.amazonaws.com/i/1po64wp676orwkwfiyx6.png)

Well, that didn't go as planned. Looks like we should have paid more attention to the documentation!

Turns out, `uniq` filters out duplicate lines that are adjacent to each other, and sends the original to `stdout`. But the password is on the *only line of text that occurs only once*
___

How do we get `uniq` to print out only those lines that occur only once in its input stream?

*Hint:* Look in the man page :)
___

Turns out `uniq` has a pretty convenient flag `-u` that ensures *only* unique lines are printed.

So the final command would be `sort data.txt | uniq -u`

![Solution](https://dev-to-uploads.s3.amazonaws.com/i/vdceuvocthez2bl7xp5b.png)

Onto the next challenge!