## Part 16: Heap

For a complete table of contents of all the lessons please click below as it will give you a brief of each lesson in addition to the topics it will cover.&nbsp;https://github.com/mytechnotalent/Reverse-Engineering-Tutorial

Our next step in the Basic Malware Reverse Engineering section focuses on the heap.&nbsp;Keep in mind, the stack grows downward and the heap grows upward.&nbsp;It is very, very important that you understand this concept as we progress forward in our future tutorials.

<div class="slate-resizable-image-embed slate-image-embed__resize-full-width"><img src="/imgs/1520241941781.jpg"/></div>

The heap is the region of your computer's memory that is not managed automatically for you, and is not as tightly managed by the CPU. It is free-floating region of memory and is larger than the stack allocation of memory.

To allocate memory on the heap, you must use __malloc()__ or __calloc()__, which are built-in C functions. Once you have allocated memory on the heap, you are responsible for freeing it by using __free()__ to de-allocate that memory once you don't need it any more.

If you don’t do this step, your program will have what is known as a memory leak. That is, memory on the heap will still be set aside and won't be available to other processes that need it.

Unlike the stack, the heap does not have size restrictions on variable size. The only thing that would limit the heap is the physical limitations of your computer. Heap memory is slightly slower to be read from and written to, because you have to to use pointers to access memory on the heap. When we dive into our C tutorial series we will demonstrate this.

Unlike the stack, variables created on the heap are accessible by any function, anywhere in your program. Heap variables are essentially global in scope.

If you need to allocate a large block of memory for something like a struct or a large array and you need to keep that variable around for a good duration of the program to which must be accessed globally, then you should choose the heap for this purpose. If you need variables like arrays and structs that can change size dynamically such as arrays that can grow or shrink as needed, then you will likely need to allocate them on the heap, and use dynamic memory allocation functions like __malloc()__, __calloc()__, __realloc()__ and __free()__ to manage that memory manually.

The next step is to dive into programming C in the Linux environment where we step-by-step disassemble each C program so in effect you will be learning both C programming and Assembly so that you can progress your skills in Malware Analysis and Reverse Engineering.

I look forward to seeing you all next week when we take a comprehensive step-by-step tutorial on how to install Linux on your current computer using the FREE Virtual Box software tool.