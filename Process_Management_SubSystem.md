# Process Management Subsystem


Process Management Subsystem

## Process:   The Process is nothing but the program running in user space of RAM

gcc filename.c  a.out  execute

--> a.out file is stored in the hard-disk, when it is executed it get loaded into the RAM. The memory segment get loaded into the user space and the PCB of the program or process get loaded into the kernel.

                                                                  (OR)

--> Whenever a program comes into execution the contents of executable binary (a.out) copied from hard-disk to user space of RAM.

### The RAM is divided into two parts:

1. User Space of RAM --> Upper part of RAM

2. Kernel Space of RAM --> Lower part of RAM

-->Whenever the program loaded into RAM , Two more memory segments are added. Those are Heap & Stack Segments.

PCB: For every process we create a block of information in kernel space of RAM is known as Process Control Block or Process Descriptor


### PCB contains:


**1. Process Identifier(PID)**

**2. Parent Process Identifier(PPID)**

    Every Process is created from another process that another process is called Parent process.

**3. File Descriptor Table(FD table)**

      It contains information about the file that are being opened by the programmer. There are many files in kernel but it does not maintains all the information of these files.

**4. Signal Disposition Table/Signal Disposition/Disposition of Signal/Signal behaviour table**

When we are hanging in the infinite loop, then we press the key to come out of the loop
i.e.
Ctrl + C ⇒ Termination
Ctrl + Z ⇒ Suspend

These combinations when used in kernel space generate the signal.

Improper handling of pointers causes crash during runtime of execution and program crashes with segmentation fault. Then this process is aborted using signaling mechanism.

**5. Page Table**

For understanding requires virtual memory and further requires paging technique and address translation.

## Process: Memory segment in user space and PCB in kernel space collectively called as process.

Process = Memory segment in user space + PCB in kernel space

## Note:
There are many process in the system, every process have their own memoery segment and they have correspondig PCB in kernel space.

  text segment= Contains Machine instruction corresponding to compiled program.
  BSS segment=Block started by symbol used to store the uninitialized global vatiables.
  Data Segment= Data segment is used to store the initialized global variables and intitalized static local variables
  
![](./Screenshot%202025-08-20%20225316.png)

## Process Creation:

There are two ways to create a Process

1. By using commands
2. By using fork() System call

### **1. By using commands**

&rarr; From the executable file process can be created by using command __./a.out__ where a.out is the executable file obtained after compilation.

![](./Executable%20file.png)

### **2. By using fork() System calls**

### System call: 
It is used in user space to send the resuest to the sub-system in kernel space. Every system call has an equivalent call in kernal space which starts with **sys_**.

&rarr; fork() system call can be used to create a child process and the process from where the fork() is invoked is called the parent process.

&rarr; Once we call fork() control immediately jumps to kernel space invoking an equivalent function in kernel starting with sys_. ofrk() is actually sending request to kernel space subsystem.

        (or)

&rarr;When we call fork() we are sending request to process management subsystem present in kernel space.(i.e, Kernel space process management)

__NOTE : -__

A Process which invoke fork system call is called **parent proccess** and the new process get created is called **child process**.

![](./images/Child%20process.png)

&rarr;Thus Page table and fd table of parent process get copied to the child process.

&rarr; parent and child process are execute different block of code.

&rarr;Before fork() invokation there is only one process but after fork() invokation there are two process i.e, child process and parent process.

