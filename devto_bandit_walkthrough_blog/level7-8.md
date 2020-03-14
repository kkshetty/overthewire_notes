Challenge page => https://overthewire.org/wargames/bandit/bandit8.html

> The password for the next level is stored in the file `data.txt` next to the word millionth

This time, the usual challenge is flipped on its head. Instead of hunting for the file that contains the password, we search for the password in the file that is given to us.

Let's take a look at the file size and the first few lines from it.

![data.txt preview](https://dev-to-uploads.s3.amazonaws.com/i/lmx42cj9n2nly5hpu6m7.png)

The file is 4 MB in size, so its quite big. Looking at the contents, a manual search will not be easy.

___

We need to find the location of a word in the file. If only there was an easy way to do this.

Hint 1: The answer for this is pretty obvious, so one web search should give you the answer. 
___


So you found it eh? Awesome. Being comfortable with the basics of `grep` is very important if you are to become comfortable with the command line. Take my word for it. It comes in handy in so many circumstances!

I would recommend glossing over the man page for `grep` before going ahead, and reading up on a few examples. 

- [Using Grep & Regular Expressions to Search for Text Patterns in Linux - DigitalOcean](https://www.digitalocean.com/community/tutorials/using-grep-regular-expressions-to-search-for-text-patterns-in-linux)

In this particular case, its a simple search, and the solution is obtained pretty easily.

![Solution found](https://dev-to-uploads.s3.amazonaws.com/i/ftmls5l810cyzsm0io72.png)

To the next challenge!