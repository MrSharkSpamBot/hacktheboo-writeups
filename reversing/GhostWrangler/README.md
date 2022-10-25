#  Ghost Wrangler
@ChallengeAuthor: clubby789 (Tony_Bamanaboni)\
@WriteupAuthor: [MrSharkSpamBot]\
**DISCLAMER: I DO NOT OWN ANY OF THE FILES IN ```rev_ghost_wrangler.zip```.**

## Description
Who you gonna call?

## Solving The Challenge
Let's run the ```ghost``` file to see what it does.
![image](img/img1.png)


Let's run the ```file``` command on the file to get general information about the file.
![image](img/img2.png)
The file is not [stripped]. This will be usefull for later.

Let's run the ```strings``` command on the file to find any interesting strings.
![image](img/img3.png)
Nothing particularly interesting.

Let's [strace] on the file to see if there is anything interesting happening in the background.
![image](img/img4.png)
Also nothing particularly interesting.


[MrSharkSpamBot]: https://github.com/MrSharkSpamBot
[stripped]: https://en.wikipedia.org/wiki/Strip_(Unix)
[ghidra]: https://github.com/NationalSecurityAgency/ghidra
[strace]: https://github.com/strace/strace
