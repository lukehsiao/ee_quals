# Philip Levis Solutions

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Philip Levis Solutions](#philip-levis-solutions)
	- [EE Quals Question 2008](#ee-quals-question-2008)
	- [Notes](#notes)

<!-- /TOC -->
## EE Quals Question 2008
1. The difference between threads and processes is that a **process** is an instance of an application and usually have their own memory space. There can be many **threads** within a process, and typically they share a memory space. A process has a virtual address space, executable code, handles to system objects, a unique process id, environment variables, priority, and at least 1 thread. A thread maintains it's own exception handlers, a scheduling priority, local storage, a unique thread identifier, and a context.

2. Considering the SMP and SMT cases...
  1. In an SMT system, option 2 might run slower because thread A and thread B might use data from different parts of memory, causing more cache misses than if we just allowed thread A to use all resources for 10ms, then thread B to use all resources for 10ms.
  2. Option 2 would run the slowest if every context switch caused a cache miss. For example, if both were operating on different chunks of data that fit perfectly in the cache, option 1 would require 1 memory load, and then all operations would use the cache. But, if in option 2, if thread A and thread B switched context after every memory access, the cache would have to be refilled every single time.
  3. In an SMP system, option 2 migh run slower if both threads are reading and editing the *same* block of memory.
  4. In the slowest case, lets say that both threads are reading and modifying every single byte in the same block of memory. In order to prevent race conditions, we would have to have a method of making sure that each thread was operating on updated data. This would likely require edits to be pushed to memory, then loaded again in the other threads cache before that thread could operate.
  5. For an SMT system, if we are operating on the same data, we would like to use option 2. If not, option 1. In an SMP system, the opposite would be true.

3. An **extent** is a contiguous area of storage reserved for a file in a file system, represented as a range. A file can consist of 0+ extents. The benefit is being able to store each range as just two numbers, rather than every block number in the range. This can also eliminate some of the metadata overhead of large files. However, the benefits in efficiency or performance are slight, but reducing metadata can reduce exposure to file system corruption.
  * Advantages:
    * Easy access, both sequential and random
    * simple
    * fewer seeks
  * Drawbacks:
    * Fragmentation makes it hard use disk space efficiently, large files may be impossible
    * Hard to predict needs at file creation time

4. TODO

## Notes
Dr. Levis is known to ask about your research as an alternative to his standard questions.
