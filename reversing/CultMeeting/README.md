# Cult Meeting

## Description
After months of research, you're ready to attempt to infiltrate the meeting of a shadowy cult. Unfortunately, it looks like they've changed their password!

## Solving The Challenge
Running the challenge file, ```meeting```, you can see that it asks for a password. The obvious answer is ```boo``` so lets try that.
![image](https://user-images.githubusercontent.com/83559791/197354672-746cdb9a-c1c3-4f78-8f8f-93834f2fe567.png)

Lets run the ```strings``` command on the file to find anything interesting.
![image](https://user-images.githubusercontent.com/83559791/197355265-d1e5a349-b01e-4532-a2bd-895cc401f79b.png)
/nNow that, seems exceptionally interesting.

Lets open the file up in [ghidra] and go to the main function.



[ghidra]: https://github.com/NationalSecurityAgency/ghidra
