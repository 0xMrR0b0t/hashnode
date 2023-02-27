# x64 Linux Assembly Language Part 3

## **What will we learn in this part?**

We're going to study system calls today. A system call is a technique used in computer programming to ask the operating system for services. These services might involve handling files, accessing physical devices, or running other applications.

While using the Linux operating system's assembly language, it's crucial to comprehend system calls. System calls are frequently employed in assembly language to carry out operations including input and output, memory allocation, and process management.

Understanding system calls can help you create more effective and efficient code by giving you a greater knowledge of how programs communicate with the operating system. By writing effective, low-level applications that can fully utilize the capabilities of the underlying hardware, you may master the use of system calls with practice.

## What are system calls?

An application can ask the operating system for services using system calls. These services might involve actions like allocating memory, starting a new process, or reading from or writing to a file.

Software enters a unique mode that enables it to communicate with the operating system when it performs a system call. The operating system then carries out the requested service and gives the program the outcome.

Modern computer programming requires the usage of system calls, which are prevalent in both high-level and low-level programming languages. Programmers may create more effective and efficient code that fully utilizes the capabilities of the underlying hardware by knowing system calls.

## How many types of system calls?

There are several kinds of system calls available in assembly language that may be used to ask the operating system for services. The individual operating system being utilized will determine the precise kinds of system calls that are accessible.

For instance, there are more than 300 system calls accessible on Linux systems, each of which has a specific number. In assembly language programming, popular system call types that are often used include:

* **System calls for input/output (I/O):** This system functions to enable a program to read from or write to a file or device.
    
* **Process management system calls:** This system calls for process management to enable a program to start, stop, or manage processes.
    
* **Memory management system calls:** This system calls for memory management **to** enable programs to allocate and deallocate memory.
    
* **System calls for time:** These system functions let a program get the current time or start a timer.
    
* **Network system calls:** The software can connect with other devices or computers via a network by using network system calls.
    

Programmers utilizing assembly language can develop more robust and effective programs that can carry out a variety of functions by being familiar with and utilizing these system calls.

## Types of input-output system calls

Input-output (I/O) system calls in x64 Linux Assembly Language enable a programme to communicate with the outside world, such as reading from or writing to a file, taking user input or printing data to the screen or printer.

Common x64 Linux Assembly Language I/O system calls include:

* `open()` – `Open()` allows you to read or write to a file by opening it and returning a file descriptor.
    
* `read()` – `read()` reads data into a buffer from a file.
    
* `write()` – `write()` is a method that outputs data from a buffer to a file.
    
* `close()` – `Close()` releases any connected resources and closes the specified file.
    
* `lseek()` – `lseek()` relocates the read/write offset inside a file to a predetermined point.
    
* `ioctl()` - I/O control operations are carried out on a device using the function ioctl().
    

Invoking these system functions often involves utilising the x64 assembly language syscall instruction.

For instance, you might use the following code in x64 Linux Assembly Language to output a string to the console:

```perl
section .data
    message db 'Hello, World!',0
section .text
    global _start
_start:
    ; write the string to stdout
    mov rax, 1 ; system call number for write
    mov rdi, 1 ; file descriptor for stdout
    mov rsi, message ; pointer to the message
    mov rdx, 13 ; message length
    syscall
    
    ; exit the program
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
```

By using I/O system calls, programmers can create powerful and flexible programs that can interact with the external world in a variety of ways.

## Types of Process management system calls

In the x64 Linux Assembly Language, system calls for process management are available for programs to start, stop, or manage processes. These system calls are crucial for controlling system resources and enhancing overall performance because they give programs the ability to direct how activities are carried out on the system.

In x64 Linux Assembly Language, some typical system calls for process control include:

* `fork()` - Fork() makes a copy of the current process and starts a new one.
    
* `exec()` - exec() switches out the active process with a different one.
    
* `exit()` - The exit() function ends the active process.
    
* `wait()` - Waits for a child process to terminate and returns the exit status of that process.
    
* `getpid()` - The function getpid() returns the process ID of the active process.
    
* `getppid()` - The function getppid() returns the parent process ID for the active process.
    

Invoking these system functions often involves utilizing the x64 assembly language syscall instruction.

For instance, you might use the code below to start a new process in x64 Linux Assembly Language:

```perl
section .text
    global _start
_start:
    ; fork a new process
    mov rax, 57 ; system call number for fork
    syscall
    
    ; check if we are the parent or child process
    cmp rax, 0 ; if rax is zero, we are the child process
    je child_process
    
    ; we are the parent process
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
    
child_process:
    ; we are the child process
    ; do some work here...
    ; then exit
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
```

By using process management system calls, programmers can create complex systems and applications that can manage multiple processes and efficiently use system resources.

## Types of Memory management system calls

In the x64 Linux Assembly Language, memory management system calls enable a program to allocate, deallocate, or manage system memory. These system calls are crucial for managing system resources and enhancing overall performance because they allow applications to dynamically allocate and manage memory as needed.

In the x64 Linux Assembly Language, some typical memory management system calls are as follows:

* `brk()` - The brk() function, which effectively allocates memory, modifies the end of the data segment.
    
* `sbrk()` - By increasing the programme break, the function sbrk() effectively allocates memory.
    
* `mmap()` - The mmap() function maps a device or file into memory.
    
* `munmap()` - munmap() removes a device or file from memory's mappings.
    

Invoking these system functions often involves utilising the x64 assembly language syscall instruction.

For instance, you might write the following code in x64 Linux Assembly Language to allocate memory:

```perl
section .text
    global _start
_start:
    ; allocate 1024 bytes of memory
    mov rax, 9 ; system call number for mmap
    xor rdi, rdi ; start address (0 = let kernel choose)
    mov rsi, 1024 ; length of memory to allocate
    mov rdx, 3 ; flags (read/write, private)
    mov r10, 0 ; file descriptor (ignored)
    mov r8, 0 ; offset (ignored)
    syscall
    
    ; check for errors
    test rax, rax
    js error
    
    ; memory allocation succeeded, do some work here...
    ; then release the memory
    mov rax, 91 ; system call number for munmap
    mov rdi, rax ; address to unmap
    mov rsi, 1024 ; length of memory to unmap
    syscall
    
    ; exit the program
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
    
error:
    ; handle error here...
    ; then exit with error code
    mov rax, 60 ; system call number for exit
    mov rdi, 1 ; return code 1
    syscall
```

By using memory management system calls, programmers can create dynamic, efficient systems and applications that can allocate and manage memory as needed, improving performance and resource usage.

## Types of System calls for time

In the x64 Linux Assembly Language, the system calls for a time to allow a program to get the current time or set the system clock. These system calls are crucial because they give programs the ability to coordinate actions across various system components and execute time-sensitive tasks.

Common system calls in the x64 Linux Assembly Language that deal with time include:

* `time()` - returns the time in seconds since the Epoch at the moment (January 1, 1970).
    
* `gettimeofday()` - The gettimeofday() function returns the time with an accuracy of one microsecond.
    
* `gettime()` - clock gettime() returns the time with an accuracy of one nanosecond.
    
* `settimeofday()` - The system clock is set with settimeofday().
    

Invoking these system functions often involves utilizing the x64 assembly language syscall instruction.

For instance, you might use the following code to get the current time in x64 Linux Assembly Language:

```perl
section .text
    global _start
_start:
    ; get the current time
    mov rax, 201 ; system call number for gettimeofday
    mov rdi, 0 ; timezone (ignored)
    mov rsi, rsp ; pointer to timeval struct in stack
    syscall
    
    ; check for errors
    test rax, rax
    js error
    
    ; print the current time (in seconds)
    mov rdi, rsp ; pointer to format string in stack
    mov rsi, [rsp + 16] ; tv_sec field from timeval struct
    xor rax, rax ; clear rax for printf
    call printf
    
    ; exit the program
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
    
error:
    ; handle error here...
    ; then exit with error code
    mov rax, 60 ; system call number for exit
    mov rdi, 1 ; return code 1
    syscall
```

By using time-related system calls, programmers can synchronize activities across different parts of a system or perform time-sensitive operations with accuracy and precision.

## Types of Network system calls

A programme can transmit or receive data, maintain network connections, and interact across a network by using network system calls in x64 Linux Assembly Language. These system calls are crucial because they give programmes the ability to communicate with other hardware, transfer data, and handle network-related tasks.

Common x64 Linux Assembly Language network system calls include:

* `socket()` - The communication socket is created via the socket() function.
    
* `bind()` - bind() gives a socket a name.
    
* `listen()` -A socket is monitored by the function listen() for new connections.
    
* `accept()` - Accepts an incoming connection on a socket using the accept() function.
    
* `connect()` - creates a connection to a remote host using connect().
    
* `send()` - send() – transmits data across a socket.
    
* `recv()` - The function recv() reads data from a socket.
    
* `shutdown()` - The shutdown() function closes a socket to new send/receive operations.
    

Invoking these system functions often involves utilizing the x64 assembly language syscall instruction.

For instance, you might use the following code in x64 Linux Assembly Language to build a socket and deliver data:

```perl
section .data
    server_addr db '127.0.0.1', 0
    server_port dw 12345
    
section .text
    global _start
_start:
    ; create a socket
    mov rax, 41 ; system call number for socket
    mov rdi, 2 ; domain (AF_INET = IPv4)
    mov rsi, 1 ; type (SOCK_STREAM = TCP)
    mov rdx, 0 ; protocol (0 = default)
    syscall
    
    ; check for errors
    test rax, rax
    js error
    
    ; set socket options (optional)
    ; ...
    
    ; connect to remote host
    mov rax, 42 ; system call number for connect
    mov rdi, [server_addr] ; pointer to server address
    mov rsi, server_port ; server port number
    mov rdx, rsp ; pointer to sockaddr struct in stack
    mov rcx, 16 ; length of sockaddr struct
    syscall
    
    ; check for errors
    test rax, rax
    js error
    
    ; send data
    mov rax, 44 ; system call number for send
    mov rdi, 0 ; socket descriptor (returned by socket/connect)
    mov rsi, data ; pointer to data buffer
    mov rdx, data_len ; length of data buffer
    mov rcx, 0 ; flags (0 = default)
    syscall
    
    ; check for errors
    test rax, rax
    js error
    
    ; close socket
    mov rax, 3 ; system call number for close
    mov rdi, 0 ; socket descriptor (returned by socket/connect)
    syscall
    
    ; exit the program
    mov rax, 60 ; system call number for exit
    xor rdi, rdi ; return code 0
    syscall
    
error:
    ; handle error here...
    ; then exit with error code
    mov rax, 60 ; system call number for exit
    mov rdi, 1 ; return code 1
    syscall
```

By using network-related system calls, programmers can create applications that can communicate over a network, exchange data with other devices, and manage network connections, enabling a wide range of network-related activities.

## Conclusion:

Programming in x64 Linux Assembly Language must include system calls. Using these calls, applications may communicate with the underlying operating system and access a variety of features, including as memory management and I/O activities.

We covered a variety of system calls in this context, including I/O, network, time, process, memory, and memory management system calls. Every sort of system call offers a varied set of functionalities and needs various inputs and outputs to perform properly.

For low-level programming and creating effective, performant apps, understanding system calls is crucial. System calls allow programmers to build network-capable programs that can share data with other devices, maintain network connections, and conduct a variety of network-related tasks. In the end, system calls are an effective tool for programmers because they give them the means to communicate with the underlying operating system and maximize x64 Linux Assembly Language programming.

If you want to view all the available system calls in x64 Linux Assembly Language, you can use the `cat /usr/include/x86_64-linux-gnu/asm/unistd_64.h` command in your terminal. This command will display the contents of the unistd\_64.h header file, which contains the system call numbers for all the available system calls in the x64 architecture.

You can also access the contents of the unistd\_64.h file using this link: [https://thevivekpandey.github.io/posts/2017-09-25-linux-system-calls.html](https://thevivekpandey.github.io/posts/2017-09-25-linux-system-calls.html)

## Note:

It's important to note that system call numbers and parameters may vary depending on the version of Linux used. Therefore, it is always recommended to refer to the appropriate header file for the specific environment you're working on to ensure that your programs are compatible and effective.