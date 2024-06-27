# ReadWriteLocks

# Custom Read-Write Lock in Java

This project demonstrates a custom implementation of a read-write lock in Java using synchronization mechanisms such as ReentrantLock and mutex to manage concurrent access to a shared resource by multiple reader and writer threads.

## Key Requirements

1. Multiple reader threads can access the resource concurrently.
2. Only one writer thread can access the resource at a time.
3. Writer threads must wait until all reader threads have finished before they can proceed.
4. Reader threads must wait if there is a writer thread writing or waiting to write.

## Overview

The program creates and manages multiple reader and writer threads that interact with a shared integer variable s. Writers can modify the value of s, while readers can only read its current value. Synchronization is achieved using ReentrantLock to prevent race conditions and ensure data consistency.

## Project Structure

The project is organized into the following classes, each in its own file within the ThreadsCheck package:

1. Main: Contains the main method to start the program.
2. ReadWriteLock: Manages the shared resource and synchronization mechanisms.
3. Reader: Implements the reader thread logic.
4. Writer: Implements the writer thread logic.

### Main Class

The Main class initializes the shared variable s, takes input for the number of reader and writer threads, and creates the respective threads. It handles invalid input and coordinates the creation and execution of threads.

### ReadWriteLock![threads example 1](https://github.com/udaarbhavana/ReadWriteLocks/assets/118459224/d8d28546-71ab-4abf-87fc-fd25bfd85982)
 Class

The ReadWrite class defines the shared variable s, locks (mutex and wrt), and methods to manage reader and writer synchronization. It includes methods to lock and unlock the write access, increment and decrement the reader count, and retrieve the shared variable's value.

### Reader Class

The Reader class implements the Runnable interface for reader threads. Each reader thread reads the shared variable s a specified number of times. It manages the reader count and ensures proper synchronization to allow concurrent reads while preventing writes.

### Writer Class

The Writer class implements the Runnable interface for writer threads. Each writer thread modifies the shared variable s a specified number of times. It ensures that only one writer can access the shared variable at a time.

## Usage

1. Compile the Java files and run the Main class.
2. Enter the initial value of the shared variable s.
3. Enter the number of reader threads.
4. Enter the number of writer threads.
5. Follow the prompts to specify the number of read and write operations for each thread.

## Example


Enter the initial value of the shared variable 's': 10
Enter the number of Readers: 2
Enter the number of Writers: 2

Creating threads...

R0 Waiting for random time between 0ns and 10ns = 5
W0 Waiting for random time between 0ns and 10ns = 3
Enter the number of times R0 wants to read: 2
R0 is reading...
R0 reads the shared value = 10
R0 reads the shared value = 10
Number of readers present = 1

Enter the number of times W0 wants to write: 1
Enter the 1th integer value to write: 5
Updated value of shared variable 's' = 15

Final value of shared variable 's' = 15


## Notes

- The program uses ReentrantLock to manage locks for reading and writing.
- Ensure proper synchronization to avoid race conditions and ensure data consistency.

## Compilation and Execution

To compile and run the program, use the following commands:

sh
javac GUVIJAVAPROJECT/*.java
java GUVIJAVAPROJECT.Main


## Conclusion

This project demonstrates the implementation of a custom read-write lock in Java, highlighting the synchronization mechanisms needed to manage concurrent access to a shared resource. It provides a foundation for understanding more complex concurrency control techniques in Java.
