Challenge page => https://overthewire.org/wargames/bandit/bandit4.html

This challenge also involves reading the password from a hidden file, which is present in the `inhere` directory.

When we navigate to the directory and list the files, there's nothing

![inhere dir contents](https://dev-to-uploads.s3.amazonaws.com/i/uoa2i1eb3dzjy5u78lsi.png)

But we know the file is there.

___
Hint 1: Once again, look at the list of the commands. Which one is likely to show us the hidden files in a directory? 
___

Didn't get it? Its ok!

___
Hint 2: Maybe [ask the Duck](https://duckduckgo.com/?t=ffab&q=show+hidden+files+in+Linux) about "show hidden files in Linux" ?
___

Yep, it was the `ls` command all along, which has an additional option to show you hidden files aka files whose names start with a dot.

![inhere dir contents](https://dev-to-uploads.s3.amazonaws.com/i/aozapsgamjofj4aixug7.png)

Congrats! Yet another flag conquered!