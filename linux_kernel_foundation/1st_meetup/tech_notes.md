
----Linux Kernel meetup (by abhya sing)----
[ Dt :: 29th september 2019 ]
  abhayksing@gmail.com
  info@linuxkernelfoundation.com

_________
cavets ::
>> when a system turns on, the boot loader(grub), initialise RAM & loads BIOS Image
  initrd(pid1) - initialise RAM Disk, with pid(Process Id) 1
  then gives an option to choose OS

>> There are basically 2 space we will talk about
  -- user space
  -- kernel space

>> when we talk about a 64 bit machine, we talk about it's address bar, and addressing capabilities
  a 64-bit m/c would have a capability of addressing a memory of size (2^64 - 1)

>> ELF :
  In computing, the Executable and Linkable Format (ELF, formerly named Extensible Linking Format),
  is a common standard file format for
    --executable files,
    --object code,
    --shared libraries, &
    --core dumps.

>> a schedular: [run queue], schedules the process to be executing

>> parent process id (PPID)

>> shared objects (.so)
  lib.c-xxxkkk---.so // beacuse we had included #include<stdio.h> the sared object (.so)

>> basically a process occupies 4 segments
    --text segments/code segments
    --data seg(bss, ds, heap & stack segments) 

>> ld  : loader

>> when a program runs, irespective of programme, CPU allocates a "page"
  generally a "page-size" is of 4kb
  page size categorised of 2 types:
    stating size (data)
    dynamic size (heap& stack)

>> profiler for c programme "gprof" (by GNU)

>> there are 4 kinds of device driver
    block device driver
    character device driver
    n/w device driver


>> linker generally links multiple shared_objects to one ELF:

>> system call: jump from user space to kernel space
  generally a system call, is something (basically an interface) to do with kernel space

>> internally in c library, stdin, stdout, stderr, are mapped to a corresponding number 0,1,2

>> eax, ebx, ecx ,, are cpu registers,, generally 'eax' corresponds to accumulator

>> every system call, have a unique number associated with it

>> mmu - memory mgt. unit is a chip in cpu

>> virtual memory :
  the concept, virtually allocates/deallocates memory
  let's say if you have 1GB of memory space, & you have 5 process, with virtual memory concepts
  each process feels that, they have 1GB memory space reserved for them,,
  -- beacuse between the process & real memory,, there is some one who stores
     corresponding ProcessID & their memory address mapper
     for which, each processs thinks they have the complete memory acess, & the man in the middle
     dynamically allocates & deallocates memory for them.
  advantage of virtual memory is::
    memory, segrigation , among proceess
    protecting physical memory from being reserved, even if the process is in sleeping state
    avoiding segmentation fault (crash, acessing unauthorised memory space)

>> kernel space is common to all, process

>> intl--switching from userspace(full acess) to kernelsoace


>> as long as the process/instruction is in user space,
    you have the complete acess over it, you can terminate it @ any time.
    but once it jump to/switch to kernel space, you have to use interrupt to halt the process

    intrupt 64hex []
    there inturpt descriptor table, available
    inturpt pin or irq number

>> Learning more about glib.c & asymbly language programme

>> directory structure :
  in /usr/src directory the source code file, and .make file stays
  .make file defines target
  various types of architecture stays in /arch directory

>> to get the various linux stable releases
  visit kernel.org
  or you can use the command to download source code from apt repository
  [apt-get source linux]

>> all kernel-space command requires sudo privilage

>> __INR_getpid

>> you can see all kenel space message in "dmessage" log file



_______________________
Commands & It's Uses ::
  ||  gcc prg1.c -o prg1   //compiles

  || file prg1
      prg1: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV),
        dynamically linked, interpreter /lib64/l,
        for GNU/Linux 3.2.0,
        BuildID[sha1]=87d50c77e0f3252b95de482c49e1b5f6c712ad1a, not stripped

  || ps -aef | grep prg1 /* comments.. **/
      if a program is in running state, you can find it's PID, with the above commands
      & then when you will go to /pid directory, you will see an folder/directory is created
      with the same name as PID & once the process is terminated, the related folder is also wiped out
      from the directory

  || cat maps | more /** process & memory mapped information */
      to find more informatioon on process, and information about it's shared objects

  || size prg1 /* tells size of the page **/
  
  || objdump -d prg1

  || cat status


  || a demo system call::
      printf("hello world ")calls(write(1, buf, sz))
      movl $SYS_write, %eax
      int 64
      ret // usys.S

  || uname -a
      the command, tells your system information

  || /usr/src$ ls -lrt
      lists all files

  || a sample system call programme
    #include <linux/kernel.h>
    asmlinkage long sys_mysSyscall(void){
      printk("my syscall implementation");
      return 0;
    }

  || a sample 'local makefile' - defines target
    obj-y := hello.o


--------------------------------------------------------------------------------------------


