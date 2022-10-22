# Cult Meeting

## Description
After months of research, you're ready to attempt to infiltrate the meeting of a shadowy cult. Unfortunately, it looks like they've changed their password!

## Solving The Challenge
Running the challenge file, ```meeting```, we can see that it asks for a password. The obvious answer is ```boo``` so lets try that.
![image](https://user-images.githubusercontent.com/83559791/197354672-746cdb9a-c1c3-4f78-8f8f-93834f2fe567.png)

Running the ```strings``` command on the file, we find an interesting string.
![image](https://user-images.githubusercontent.com/83559791/197355265-d1e5a349-b01e-4532-a2bd-895cc401f79b.png)

Lets open up the ```meeting``` file up in [ghidra] and go to the main function to try to find out the use of this string.
![image](https://user-images.githubusercontent.com/83559791/197364361-afe5c096-0649-4c05-a717-5cdc276e15c7.png)

The decompiled main function is the following:
```c++
undefined8 main(void)

{
  int iVar1;
  char *pcVar2;
  char local_48 [64];
  
  setvbuf(stdout,(char *)0x0,2,0);
  puts("\x1b[3mYou knock on the door and a panel slides back\x1b[0m");
  puts(&DAT_00102040);
  fwrite("\"What is the password for this week\'s meeting?\" ",1,0x30,stdout);
  fgets(local_48,0x40,stdin);
  pcVar2 = strchr(local_48,10);
  *pcVar2 = '\0';
  iVar1 = strcmp(local_48,"sup3r_s3cr3t_p455w0rd_f0r_u!");
  if (iVar1 == 0) {
    puts("\x1b[3mThe panel slides closed and the lock clicks\x1b[0m");
    puts("|      | \"Welcome inside...\" ");
    system("/bin/sh");
  }
  else {
    puts("   \\/");
    puts(&DAT_00102130);
  }
  return 0;
}
```

The string previous found by the ```strings``` command is the password for the meeting. The [strcmp] function is being used to check if the value read from standard input and the string ```sup3r_s3cr3t_p455w0rd_f0r_u!``` are equivalent.

Lets try this password.
![image](https://user-images.githubusercontent.com/83559791/197364508-75a991ec-a33e-4aab-8c72-9f0abfc0f822.png)

Now that we know the password works, we can spawn the docker container and connect to it using netcat in order to find the flag.
![image](https://user-images.githubusercontent.com/83559791/197364594-5da68a3f-4467-4f23-a3da-983e9d3b6ceb.png)


[ghidra]: https://github.com/NationalSecurityAgency/ghidra
[strcmp]: https://man7.org/linux/man-pages/man3/strcmp.3.html
