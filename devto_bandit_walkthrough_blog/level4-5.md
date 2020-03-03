Challenge page => https://overthewire.org/wargames/bandit/bandit5.html

This time, we try to read the password from the "only human-readable file in the inhere directory."

Read that part in the quotes twice. By now, you should be used to the fact that there is a subtle hint in here, and among the list of commands you may need

> ls, cd, cat, file, du, find

Now, lets take a look at the contents of the directory to see what all the fuss is about, and try reading a file or two

![Contents of inhere directory](https://dev-to-uploads.s3.amazonaws.com/i/xtwl7oqoj1ymukf1yayh.png)

Ha! That's why they mentioned "human-readable"! The files seem to contain binary data, which cannot be read by programs(cat etc) designed to read text files.

So, we can either go through all of them one by one to see which one has text, or we find an easier way to filter out the one file among the 10 that contains text

___
Hint 1: Try and figure out which of the "commands you may need" listed earlier can be used here to solve our problem. Try reading their man pages. :)
___




This one's quite obvious eh? 

The `file` type comes in very handy in such situations. Let's go ahead and run it on the entire directory to figure out which file has the password.


![Check file type and display password](https://dev-to-uploads.s3.amazonaws.com/i/1a7vupy4seh2jo2thkfi.png)


Aaand there we have it. Onto the next challenge!