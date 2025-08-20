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

