# Assembly_language_tuturiol
Assembly Language Tuturiol


Hello every i hope y are doing well on this process  of  learning assembly language i will  share with my step and process of learning assembly  language  on this journey  i wil share with u lessons that i learn  every  day and share theme with the community the topis consider as challange to me :)
I hope u gone  like this concept and encorage me & i would like  ur pint  of view and encouragemnt , because i am not an expert inam  still  learning


#First lesson is Sum of nuber in array  in assembly 

The following example demonstrates the above concepts by defining a 3-element array x, which stores three values: 2, 3 and 4. It adds the values in the array and displays the sum 9 −

The source code  :

section	.text
   global _start   ;must be declared for linker (ld)
	
_start:	
 		
   mov  eax,3      ;number bytes to be summed 
   mov  ebx,0      ;EBX will store the sum
   mov  ecx, x     ;ECX will point to the current element to be summed

top:  add  ebx, [ecx]

   add  ecx,1      ;move pointer to next element
   dec  eax        ;decrement counter
   jnz  top        ;if counter not 0, then loop again

done: 

   add   ebx, '0'
   mov  [sum], ebx ;done, store result in "sum"

display:

   mov  edx,1      ;message length
   mov  ecx, sum   ;message to write
   mov  ebx, 1     ;file descriptor (stdout)
   mov  eax, 4     ;system call number (sys_write)
   int  0x80       ;call kernel
	
   mov  eax, 1     ;system call number (sys_exit)
   int  0x80       ;call kernel

section	.data
global x
x:    
   db  2
   db  4
   db  3

sum: 
   db  0
   


Compiling and Linking an Assembly Program in NASM
  Make sure you have set the path of nasm and ld binaries in your PATH environment variable. Now, take the following steps for compiling and linking the above program −

  Type the above code using a text editor and save it as file_name.asm.

  Make sure that you are in the same directory as where you saved hello.asm.

  To assemble the program, type nasm -f elf file_name.asm

  If there is any error, you will be prompted about that at this stage. Otherwise, an object file of your program named file_name.o will be created.

  To link the object file and create an executable file named file_name, type : ld -m elf_i386 -s -o file_name file_name.o

  Execute the program by typing ./file_name
  
  Make sure that your are  privileged to run those command .
