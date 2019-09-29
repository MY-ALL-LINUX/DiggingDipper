
----Liniux Kernel meetup (abhya sing)----
[ Dt :: 29th september 2019 ]



boot loader (BIOS) [grub] []prepares-os

grub::
init rd(pid1), 




_________
systemcall implementation
kernel space, user space

gcc prg1.c -o prg1

eELF

file prg1
prg1: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/l, for GNU/Linux 3.2.0, BuildID[sha1]=87d50c77e0f3252b95de482c49e1b5f6c712ad1a, not stripped
subrat@palmatesolution:~/Desktop/subrat/a_learing/Linux$ 

2^64 - 1


schedular: run queue
parent process id (PPID)

ps -aef | grep prg1 //


process is stored in files pid directory with process-id folder







cat maps | more //process & memory mapped information


shared objects:
4 segments s:: text segments/code  segments, data seg(bss, ds, heap & stack segments), 




shared objects (.so)



lib.c----.so
ld  : loader


page size (4kb)

size prg1


stating size (data)
dynamic size (heap& stack)


objdump -d prg1




cat status




profileer :: gprof - 
system calls api : 

..
block device driver
character device driver 
n/w device driver



multiple objecys to one ELF:
linker





linking time, 


system call: jump from user space to kernel space


file descriptor : 0.1.2 (stdin, out, err)


accumulator (eax)



ebbry system call have a unique numbr 



printf("hello world ")calls(write(1, buf, sz))

movl $SYS_write, %eax
int 64
ret // usys.S



mmu - memory mgt. unit chip


vertual memory: memory \segrigation , among pr\oceess id
protecting physical memory from being locked
segmentation fault (crash, acessing unauthorised memory space)

kernel space is common for all

intl--switching from userspace(full acess) to kernelsoace
intrupt 64hex []
inturpt descriptor tabvle


inturpt pin or irq number



glib.c


asymbly

eax,rx,ex

uname -a
/usr/src$ ls -lrt




directory structure :

architecteire /arch directory (arm wi)






system call - interface , to do with kernel space




vx box, cypher


kernel.org
apt-get source linux





create ur own directory
write a .c program

#include <linux/kernel.h>
asmlinkage long sys_mysSyscall(void){
  printk("my syscall implementation");
  return 0;
}

makefile - build the ytarget
obj-y := hello.o







kernel space :: sudoo privilage

ifeq 



__INR_getpid




dmessage



abhyksing@gmail.com



info@linuixkernelfoundation.com


