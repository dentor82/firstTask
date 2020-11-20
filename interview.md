0. Introduction
   0. Talk about previous experience.
       0. What project you were involved in?
       0. What tasks you were solving?
       0. What approaches you were applying?
       0. Technologies stack?
   0. English skills
   0. What is the future plans? Perfomance engineer, architect/tech lead, code monkey, smth else

0. Tech.

   -- Java core

   0. Collections.
       0. Map
           - what types do you know in Java?
           - what's the difference between the types?
           - what is preffered in different cases?
           - Object charateristics to be a key in a HashMap/TreeMap, hash code features
           - Sets
       0. List
           - what types do you know in Java?
           - what's the difference between the types?
           - what is preffered in different cases?
       0. Queue, Deque, Stack
       0. PriorityQueue (senior level)

   0. Multi-threading
       0. What is the purpose? Is there any cases when perfomance reduces? What is thread-safe code?
       0. Ways to create threads in Java: new, pooling (executors).
       0. Issues that causes: deadlocks, race conditions (deadlock, livelock, starvation).
       0. What can help:
           - synchronize, immutability, volatile, lock-free collections, blocking queue, atomic operations,
           - monitors, more precise tools (read-write lock, semaphore, cyclic barriers, count down latch) (senior level)
       0. fork-join/map-reduce
       0. futures
       0. Timer vs ScheduledThreadPoolExecutor (senior level)
       0. Java 8 Concurrent collections
       0. ForkJoinPool

   0. Exceptions
       0. What types in Java?
       0. How to use them?
       0. Working with errors: C-style vs Exceptions?

   0. Memory management.
       0. Garbage collector.
           - What is it, what's it for?
           - Memory leaks. When it's happened, how to prevent.
           - generations, algorithm of collecting, difference between java 6 and 8 (senior level)
       0. Object lifecycle in Java. (senior level)
           - what to do on finalize? ability to resurrect object?

   0. Java features (mostly senior level)
       0. cloneable
       0. serializable/externalizable
       0. default constructors, static constructors
       0. class loaders
       0. Phantom/Soft/Weak references. (very optional)
       0. new Long(ANY_NUMBER) vs Long.valueOf(ANY_NUMBER), comparing of primitive wrappers, auto-boxing.
       0. String.intern()

0. Spring
	0. container
	0. spring-boot
	0. spring-security
	0. zuul/netflix stack

   -- DBMS
   0. What DBMS did you work with?
       0. familiar with most constructions
           - stored procedures?
           - joins, differents between them, different syntax?
           - group, having, aggregate functions?
           - union, union all?
           - joins vs subqueries
       0. relational vs non-relational
   0. Indexes.
       0. What for? Any side effect? Slower inserts?
       0. Composite index vs several separate indexes. (senior level)
   0. Multi-thread usage. Transaction isloation. Deadlocks
   0. Practical task: the approach you'll use to insert a lot of records into a table.

   -- General
   0. Code Patterns
       0. Design patterns, are they useful? why?
       0. Abstract class vs Interface
       0. Singleton pros and cons.
       0. Dependency Injections

   0. TDD, BDD approaches
       0. did you use it? your feelings about that?

       