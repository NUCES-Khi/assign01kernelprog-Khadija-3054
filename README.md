[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-8d59dc4de5201274e310e4c54b9627a8934c3b88527886e3b421487c677d23eb.svg)](https://classroom.github.com/a/m2pJ6e_2)

## All commands used for the assignment:

![1](https://user-images.githubusercontent.com/126002605/228139298-235c2769-d17d-4266-9e7f-d58d70ce59c2.jpg)



## All steps

1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'.

2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively

3: In hello.c write this code #include <linux/kernel.h> asmlinkage long sys_hello(void) { printk("Hello world\n"); return 0; }

4: In Makefile add this obj-y := hello.o

5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file

6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file.

![123](https://user-images.githubusercontent.com/126002605/228139466-f5282d8d-6861-4ffc-b267-2b7b553bfd42.png)


7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype of our system call function in this file.

8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it.

![321](https://user-images.githubusercontent.com/126002605/228139524-c9b089ea-c93b-410a-8418-5db3f3e611c9.png)


9: Open Makefile and in Extraversion put the value equal to the roll number

10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/"

![56465](https://user-images.githubusercontent.com/126002605/228139565-4c8465a9-f9dd-4d92-8697-5d5735974c0b.png)



11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory”

12: We will now write the configuration file

13: We have to clean our processes in the kernel by typing “make clean -j1” , we now type “make -j1” to start building our kernel and then install modules through command "make modules_install install".

14: now we will restart ubuntu and then choose ubuntu version with our roll number

15: write "uname -r" in ubuntu to check if you have done correctly

![2](https://user-images.githubusercontent.com/126002605/228139610-9c560457-f76e-4383-b6c9-f20b46c94d34.jpg)



16: now make a c file and write the following code to check if the system call you made works

17: you can verify through writing "dmesg" in terminal

![3](https://user-images.githubusercontent.com/126002605/228139644-e83a8d60-1276-4130-a986-c9e33e26b279.jpg)


