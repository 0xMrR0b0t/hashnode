# x64 Linux Assembly Language Part 2

## What will we learn in this part?

Welcome to the second part of the X64 Linux Assembly Language blog! The goal of this blog is to educate readers about the intricate world of x64 assembly language. We'll be concentrating on Data Types and Memory Access in this blog.

We will talk about how data is stored in memory and how the x64 architecture supports different data kinds including characters, integers, and floating-point numbers. We'll also go through how to use commands like MOV, LEA, and PUSH/POP to load and save data into memory.

**Our articles on this topic will cover:**

1. Introduction to Data Types and Memory Access
    
2. Representing Data in Memory
    
3. The x64 Architecture and Data Types
    
4. Loading and Storing Data in Memory
    
5. The MOV Instruction
    
6. The LEA Instruction
    
7. The PUSH/POP Instructions
    

We hope that you find our writings to be both educational and practical. Our goal is to increase the simplicity and accessibility of learning x64 assembly language. Therefore be on the lookout for more fascinating writings on this subject!

## Introduction to Data Types and Memory Access

Two fundamental ideas in computer science are Data Types and Memory Access. Memory access, also known as data types, describes how the computer accesses and manages the different types of data that are stored in memory.

To put it simply, data types are containers that may carry various kinds of information. Although age is a whole number, we would use an integer data type if we wanted to keep a person's age in memory. Similarly to this, since names are composed of distinct characters, a character data type would be used to store a person's name.

Integers, floating-point numbers, and characters are only a few of the data kinds that the x64 architecture offers. These data types are represented in memory by a collection of bits and bytes that, depending on the data type, are arranged in particular patterns.

Memory access describes how a computer interacts with information that is kept in memory. This entails bringing data from memory into the CPU, processing it with a variety of instructions, and then returning the data to memory.

Let's take the case when we wish to combine two numbers. The two integers would be loaded into the Processor using the MOV instruction as the first step. After combining the two integers using an instruction like ADD, we would once more use the MOV instruction to store the outcome back in memory.

In summary, knowing how computers store and process data requires a comprehension of two key computer science concepts: data types and memory access. These ideas help us better comprehend how computers operate and how to create effective and efficient code.

## Representation of Data in Memory

There are several ways that data may be shown and kept in memory. These are a few of the most typical approaches:

* **Binary:** The simplest way to store data in memory is in binary form. To represent all data, it just utilizes the numbers 0 and 1. Each digit is referred to as a bit (short for binary digit), and a byte is made up of 8 bits. For instance, 01000001 may be used to represent the letter "A" in binary.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677223777791/91d30c1b-fed1-4746-a2f1-0b18bbd3bf16.png align="center")
    
* **Decimal:** We always utilize the decimal method of numbers. To represent all integers, it needs ten digits, from 0 to 9. Each decimal digit in memory is typically represented by 4 bits. The memory representation of the number 42, for instance, would be 0010 1010.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677223877017/4adb370f-105e-42b5-b572-290f2716d824.png align="center")
    
* **Hexadecimal:** Hexadecimal uses 16 digits to represent all numerals, including 0 through 9 and A through F. As a result of its simplicity in reading and writing, it is frequently employed in computer programming. Typically, 4 bits are used to represent each hexadecimal numeral. The hexadecimal representation of the color white, for instance, is #FFFFFF, which would be stored in memory as 1111 1111 1111 1111 1111.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677223936287/ce7cf134-3a01-43d7-8705-b91a82ca2860.png align="center")
    
* **ASCII:** The ASCII standard uses 7 bits to represent characters (letters, numerals, and symbols). There are 128 distinct characters that it can represent in total, including all capital and lowercase letters, numerals, and certain symbols. For instance, the ASCII code for the letter "A" is 01000001.
    
* **Unicode:** This is a more sophisticated character representation standard that can support a wide range of writing systems and languages. Almost 1 million different characters may be displayed because of its up to 4-byte character representation.
    

In conclusion, data may be stored in memory in a number of different formats, including binary, decimal, hexadecimal, ASCII, and Unicode. Depending on the requirements of the application, each approach is utilized in various contexts and has a variety of benefits and drawbacks.

## The x64 Architecture and Data Types

Modern computers frequently employ the x64 architecture, a sort of CPU architecture. Since it enables 64-bit computing or the processing of data in greater chunks than prior 32-bit processors, it is known as an x64 processor. The following are some frequent data types used in x64 architecture:

* Integers: Positive or negative whole numbers with no further decimal places are known as integers. In the x64 architecture, 64 bits (8 bytes) of memory are often used to hold integers. The range of numbers they may represent as a result is enormous, ranging from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. The memory address for the integer 42, for instance, would be 00000000 00000000 00000000 00000000 00000000 00000000 00101010.
    
* Floating-point numbers: Numbers with decimal places are referred to as floating-point numbers. Floating-point integers are often stored in x64 architecture utilizing 64 bits (8 bytes) of memory. They may thus represent a very broad range of values, covering both very small and very high integers. For instance, the memory address for the floating-point number 3.14159 would be 01000000 00010010 01000100 00100001 01111101 11011100 01010100 00001111.
    
* Characters: Individual letters, numbers, or symbols are referred to as characters and are used to represent text. Characters are typically stored in x64 architecture utilizing 8 bits (1 byte) of memory. They may now represent 256 distinct characters altogether thanks to this. For instance, the memory would store the letter "A" as 01000001.
    
* Pointers: Memory addresses are stored in pointers, which are variables. Pointers are typically stored in 64 bits (8 bytes) of memory in the x64 architecture. They are frequently used to refer to other variables or memory-based data structures. An integer variable pointer, for instance, might be stored in memory as 00000000 00000000 00000000 00000000 00000000 00000000 00000000 00000000 00101010 00000000.
    

In summary, the x64 architecture supports a wide range of data types, including pointers, characters, floating-point numbers, integers, and more. The amount of bits used to store each data type in memory influences the range of values that may be represented by that data type. The x64 architecture enables very big and complex data structures to be handled rapidly and effectively since it supports 64-bit computation.

## Loading and Storing Data in Memory

Moving data in and out of a computer's memory is referred to as loading and saving data. Data must first be loaded from memory into the processor before a software may use it for manipulation. The software must also put the data back in memory when it has finished processing it so that it may be stored or utilized at a later time.

It's similar to setting up books on a desk to be read to load data into memory. A register—sort of like a temporary holding space for the data that the processor is now using—is where the processor loads a specific piece of requested data from memory once the processor requests it. After loading the data into the register, the processor may work with it.

Comparable to placing books back on a bookshelf is storing data in memory. After utilizing the data, the CPU returns it to the proper region in memory for storage. This makes sure the information is kept for subsequent use and is accessible again if necessary.

Consider working on a computer program that has to add two integers together as a simple illustration. The two integers must first be loaded from memory into the processor's registers so that they may be added. The outcome of the computation is then saved back into memory for future use.

In summary, loading and saving data in memory is a fundamental process that is required by any computer program. It guarantees that data is preserved for later use and enables computers to alter data and carry out computations. The procedure is comparable to placing books on a desk to read them and then returning them to a bookshelf once you are through.

## The MOV Instruction

Data can be moved between registers and memory using the fundamental assembly language instruction MOV. It is frequently used to load or store data into and out of memory, initialize variables, and move values across memory regions.

The MOV instruction has the following fundamental syntax:

```yaml
MOV destination, source
```

the operands being a `destination` and `source`. Both the `source` operand and the `destination` operand provide the data that has to be `transported`, together with the location of that data.

An example of an assembly language program using the MOV instruction is shown below.

```yaml
MOV RAX, 5
```

The `RAX register` is updated with the value 5 by this instruction. A 64-bit register called the `RAX register` is used to store integer values.

Here is another illustration of how to transfer a value to a register from memory:

```apache
MOV RAX, [variables]
```

The value kept in memory location variables is transferred to the `RAX register` by this instruction. The value should be read from memory, as indicated by the square brackets surrounding var.

Here is a final illustration that transfers a value from a register to a memory location:

```apache
MOV [variables], RAX
```

This instruction transfers the `RAX registers` value to the memory location variables. Variables are marked with square brackets to indicate that the value has to be written to memory.

The MOV instruction, in short, is a fundamental assembly language instruction used to transfer data between registers and memory. It may be used to load or store data into or out of memory, initialize variables, and move values across memory regions. It requires two operands, a source and a destination.

## The LEA Instruction

In x86 assembly language programming, the **<mark>LEA (Load Effective Address)</mark>** instruction is a machine language instruction that is often utilized. The LEA instruction's goal is to determine a memory operand's effective address or the address at which the information is stored in memory. The location at which the data is saved, not the data itself, is the outcome of the LEA command.

The LEA instruction has the following syntax:

```yaml
LEA destination, source
```

where the source is the memory operand for which the effective address will be computed and the `destination` is the register that will carry the effective address.

Using the LEA instruction is demonstrated in the following way:

```apache
MOV EAX, [EBX+ECX*4+8]
LEA EDX, [EBX+ECX*4+8]
```

In this example, the memory location `[EBX+ECX*4+8]` is loaded using the MOV instruction to load a 32-bit value into the EAX register. The EDX register maintains the effective address of the same memory operand, which is calculated by the LEA instruction.

An example of an addressing mode is the equation `[EBX+ECX*4+8]`. After multiplying the value of the EBX register by four times that of the ECX register, the result is increased by eight. The memory operand's effective address is determined by this expression.

The effective address of the memory operand, which is the location where the data is kept in memory, is `[EBX+ECX*4+8]` and is put in the EDX register following the execution of the LEA instruction.

## The PUSH and POP Instructions

The PUSH and POP commands in x64 assembly language programming are used to work with the stack. The employment of the PUSH/POP instructions is, however, impacted by the way registers are handled as function parameters in the x64 calling convention.

On x64, the first few function arguments are given in registers rather than on the stack, and subsequent arguments are passed on the stack. Moreover, some registers are marked as "callee-save" registers, which means that the callee (the function being called) is in charge of storing their contents prior to modification.

The PUSH instruction's syntax in x64 assembly is as follows:

```apache
PUSH destination
```

where `destination` refers to the memory or register location that will be placed into the stack.

Using the PUSH instruction in x64 assembly is demonstrated in the following example:

```apache
MOV RAX, 10 ; move value 10 into RAX register
PUSH RAX    ; push RAX onto the stack
```

In this case, the number 10 is initially placed into the RAX register before being pushed into the stack using the PUSH command.

Here is the syntax for the POP example in x64 assembly:

```apache
POP destination
```

where `destination` is the register or memory address where the value that was popped from the stack will be stored.

Here is an example of how the POP instruction is used in x64 assembly:

```apache
POP RAX     ; pop a value from the stack into RAX
ADD RAX, 5  ; add 5 to the value in RAX
```

In this case, a value is pulled from the top of the stack and stored in the RAX register using the POP command. The value in RAX is then increased by 5 using the ADD instruction.

# **Conclusion**

Understanding data types and memory access is essential for programming in any language, including assembly language. Efficient use of memory can significantly impact the performance of programs. Additionally, knowledge of the x64 architecture and instruction set is crucial in developing assembly language programs for modern processors. Loading and storing data in memory, as well as utilizing instructions like MOV, LEA, PUSH, and POP, are all critical aspects of assembly language programming. By mastering these concepts, programmers can develop optimized, efficient, and high-performance assembly language programs.

That's all! Thank you for getting this far. I hope you find this article useful.