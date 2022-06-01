# Hacking using C-Language
To look at the machine code of a gcc compiled program, we can use objdump
Example command:
objdump -D {filename} | grep -A20 main.:
Example output:
0000000000001149 <main>:
    1149:	f3 0f 1e fa          	endbr64 
    114d:	55                   	push   %rbp
    114e:	48 89 e5             	mov    %rsp,%rbp
    1151:	48 83 ec 10          	sub    $0x10,%rsp
    1155:	c7 45 fc 00 00 00 00 	movl   $0x0,-0x4(%rbp)
    115c:	eb 13                	jmp    1171 <main+0x28>
    115e:	48 8d 05 9f 0e 00 00 	lea    0xe9f(%rip),%rax        # 2004 <_IO_stdin_used+0x4>
    1165:	48 89 c7             	mov    %rax,%rdi
    1168:	e8 e3 fe ff ff       	call   1050 <puts@plt>
    116d:	83 45 fc 01          	addl   $0x1,-0x4(%rbp)
    1171:	83 7d fc 09          	cmpl   $0x9,-0x4(%rbp)
    1175:	7e e7                	jle    115e <main+0x15>
    1177:	b8 00 00 00 00       	mov    $0x0,%eax
    117c:	c9                   	leave  
    117d:	c3                   	ret    

Disassembly of section .fini:

0000000000001180 <_fini>:
    1180:	f3 0f 1e fa          	endbr64 


The objdump program displays alot of instructions thats why we just grep the useful information inside the main() function.
Each bytes is represented in hexadecimal notation(base-16 numbering system), This is a convenient notation because a byte contains 8 bits. Each of which can be either true or false.
This means that a byte has 256 possible values so each byte can be described with 2 hexadecimal digits.
The hexadecimal numbers on the far left are memory adresses. The machine language instructions are put on the memory(A collection of bytes of temporary storage space that are numbered with addresses.)

