Challenge page => https://overthewire.org/wargames/bandit/bandit3.html

This challenge is very similar to the previous one, as it also involves reading the password from a file with a tricky file name.

The file name where the password resides contains spaces. Now if you've ever had anything to do with filenames on the command lines, you already know how to do this. Its all right if you don't know. By the end of this, you will!

----

Hint 1: Just google it! "How to read filenames with spaces". There are multiple ways to do this.


----

You found it didn't you? Awesome.

There's basically two ways you can read a file whose name contains spaces. Both ways ensure that your shell does not interpret the words in the file name as command arguments.

###Solution

The first way is to escape the spaces with a backward slash.

The second way is to place quotes around the filename. Both are shown in the below picture.

![bandit3](https://thepracticaldev.s3.amazonaws.com/i/woji8q40e7d96wrnplto.png)

P.S: You can also get the shell to autocomplete the filename for you, by typing a couple of letters in the first word of the file name, and then pressing `TAB`

Happy Hacking!

