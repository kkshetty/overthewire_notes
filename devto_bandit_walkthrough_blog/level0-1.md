Challenge page => https://overthewire.org/wargames/bandit/bandit1.html

A piece of info to keep in mind to avoid any confusion.

When a Bandit Level is called Level X -> Level Y, it means you need to use the credentials for Level X aka banditX **which you already possess**, to acquire the password for Level Y aka the user banditY.

In our case, we have the credentials for bandit0, so we need to get the password for bandit1 using this.

Now that it's all cleared up, let's read the instructions.

>The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

**PAY PARTICULAR ATTENTION TO THE BELOW SECTION**
>Commands you may need to solve this level
>ls, cd, cat, file, du, find


In many cases, when you are left scratching your heads over what to do next, the list of commands is where the designers leave a subtle clue. So never ignore it.

Hint 1: You need to login as bandit0 and then get the password stored in the file named "readme". Which command do you think is best to display the contents of the file?

---

Hint2: This is an easy challenge. Try googling it, or even better [ducking it!](https://duck.com)

---

Pretty sure you figured it out :). Even so, here's the solution

![bandit1](https://thepracticaldev.s3.amazonaws.com/i/lodvkitffmt1fmm4dpfb.png)
