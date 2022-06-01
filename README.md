# Hacking using C-Language
To look at the machine code of a gcc compiled program, we can use objdump
Example command:
objdump -D {filename} | grep -A20 main.:
Example output:
![image](https://user-images.githubusercontent.com/42641723/171374873-26c895fb-0d4f-40a0-aacf-8722fd2a1bae.png)


The objdump program displays alot of instructions thats why we just grep the useful information inside the main() function.
Each bytes is represented in hexadecimal notation(base-16 numbering system), This is a convenient notation because a byte contains 8 bits. Each of which can be either true or false.
This means that a byte has 256 possible values so each byte can be described with 2 hexadecimal digits.
The hexadecimal numbers on the far left are memory adresses. The machine language instructions are put on the memory(A collection of bytes of temporary storage space that are numbered with addresses).
You can think of memory as a row of bytes, each with its own memory address. Each byte of memory can be access by its address, Here the CPU accesses this part of memory to retrieve the machine language instructions for the compiled program.
Older Intel x86 processors use a 32-bit addressing scheme, while newwer ones use a 64-bit one. 32-bit processors have 2^32 possible adresses(4,294,967,296), 64 bit ones have 2^64(1.84467441x10^19)addresses.
64-bit processors can run in 32-bit compatibility mode which allows them to run 32-bit code quickly.
 
