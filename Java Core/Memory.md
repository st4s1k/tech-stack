1. [[#Heap]]
	1. [[#Method Area]]
2. [[#Stack]]
	1. [[#JVM Stacks]]
	2. [[#Native Method Stacks]]
3. [[#GC]]
4. [[#Sources]]

![[jvm_memory.png]]
### Heap

- Heap is a shared runtime data area where objects and arrays are stored. It is created when the JVM starts.
- The memory in the heap is allocated for all the class instances and arrays.
- Heap can be of fixed or dynamic size depending upon the system’s configuration.
- JVM allows user to adjust the heap size. When the new keyword is used the **object is allocated in the heap** and **its reference is stored in the stack.***
- There exists one and only one heap for a running JVM process.
```java
Scanner sc = new Scanner(System.in)
```
Here, the **Scanner** object is stored in the heap and the reference **sc** is stored in the stack

> **Note:** Garbage collection in heap area is mandatory.

#### Method Area

- Method area is a logical part of the heap and it is created when the JVM starts.
- Method area is used to store **class-level information** such as [class structures](https://www.geeksforgeeks.org/classes-objects-java/), [Method bytecode](https://www.geeksforgeeks.org/byte-code-in-java/), [Static variables](https://geeksforgeeks.org/static-variables-in-java-with-examples/), [Constant pool](https://www.geeksforgeeks.org/string-constant-pool-in-java/), [Interfaces](https://www.geeksforgeeks.org/interfaces-in-java/).
- Method area can be of fixed or dynamic size depending on the system’s configuration.

> **Note:** Though method area is logically a part of heap, it may or may not be garbage collected even if garbage collection is compulsory in heap area.

### Stack
#### JVM Stacks

- A stack is created when a [thread](https://www.geeksforgeeks.org/java-threads/) is created, and the JVM stack is used to store method execution data, including local variables, method arguments, and return addresses
- Each Thread has its own stack, ensuring thread safety.
- Stacks size can be either **fixed** or **dynamic**, and it can be set when the stack is created.
- The memory for stack needs not to be contiguous.
- Once a method completes execution, its associated stack frame is removed automatically.
#### Native Method Stacks

- Native method stack is also known as **C stacks.**
- Native method stacks are not written in Java language
- This memory is allocated for each thread when it is created and can have either a **fixed** or **dynamic** size.
- Native method stacks handle the execution of **native methods** that interact with the Java code.
### GC

The **Garbage collector** in Java automatically removes the unused objects that are no longer needed. It runs in the background to free up memory.

- Garbage collector finds objects that are no longer needed by the program.
- It removes those unused objects to free up the memory and making space for new objects.
- New objects are collected more frequently than older objects, which helps improve efficiency.
- You can request garbage collection using **`System.gc()`**, but the JVM ultimately decides when it should run.

> **Note:** **System.gc()** and **Runtime.gc()** are the methods which requests for Garbage collection to JVM explicitly but it doesn’t ensures garbage collection as the final decision of garbage collection is of JVM only.
### Sources

1. [Java Memory Management - GeeksforGeeks](https://www.geeksforgeeks.org/java-memory-management/)