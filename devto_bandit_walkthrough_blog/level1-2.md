Challenge page => https://overthewire.org/wargames/bandit/bandit2.html

This challenge also involves reading a file to get the password, but it has a tricky file name. 

***

**Hint 1**: Your `cat` command did not work, did it? :D It's ok. That's what this challenge is about.

Technically the cat command is working fine. As for why it did not read the file "-", once again the hints have been provided by the designers in the form of links for further reading.

> [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
> [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)


***

**Hint 2**: The first result of the Google search, which leads to a Unix Stack Exchange post explains the problem and gives you the answer as well.

***

###Solution

No more hints as you already have the answer :)

By now you've figured out that cat is treating "-" as a synonym for stdin. 

As for what exactly cat is doing, [go to the second link](http://tldp.org/LDP/abs/html/special-chars.html), and Ctrl+F for "*redirection from/to stdin or stdout [dash]*". It will lead you to a section that explains `cat`'s behaviour, and other scenarios where the "-" is used by other commands

I would also recommend browsing the same article for info on the other special characters mentioned there.

As was shown in the Unix Stack Exchange post, the solution is to simply use the full path to the file like below, which ensures cat does not treat it as stdin

![bandit3](https://thepracticaldev.s3.amazonaws.com/i/vkge6n306is45vnajh2p.png)