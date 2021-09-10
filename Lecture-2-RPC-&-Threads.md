Go has convenient RPC package, and support for threads.
Unlike C++, GO is type safe, memory safe, and garbage collection.

Concurrency is important in DS because a server may be talking to multiple clients, or other way, and we may need to keep in contct with. Go calls threads "go routines"

## Serial Programs
- Sequential execution on single thread

## Threaded Program
- Multiple threads, with separate set of registers, program counter, and separate stack. So threads can be independent.

- Threading also helps in multi core parallelism. A compute heavy job can be divided in multiple threads and run parallelly on same machine.

- Process vs threads: A Process is a single program that is running and has a single address space/memory for the process, and inside the process you may have multiple threads running.

- Within a program threads can share memory if they want to but not across programs.

Thread Challenges:
- Shared memory between threads can create data race. To solve this we can use locks. Go calls locks mutexes, you can wrap code in a lock like. Or Fix your code to not share data!
```
mu.lock()
n = n+1
mu.unlock()
```
- Co-ordination. Solved with-> In go you can use channels, wait Group, and sync cond
- Deadlock (T1 is waiting on T2, and T2 is waiting for T1)

# Web Crawler
- Goal is to go to a url and find nested urls and keep crawling.
- We want to avoid cyclic graphs.
- Challenge can be to figure out when we have crawled every single page.

