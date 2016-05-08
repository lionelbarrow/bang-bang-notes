# Storing your data in kernel space - an excellent bad idea!

Kamal Marhubi

Ordinarily when writing programs, we want to keep memory usage low. We don't like when Firefox uses 2gb of memory on a 4gb laptop.

Let write a program that stores lots of data in memory without using a lot of memory. To do this we'll store it in kernel memory.

Kernel memory is mostly book-keeping process state. Modern computers have a special piece of hardware, the memory management unit (MMU), which prevents user programs from using kernel memory. To get around this, we'll store the data in pipes.

When data is going through a pipe, it's stored in kernel memory. User processes only have pointers to the data as a file descriptor. So, how can we get a random access buffer from a pipe? Well, just read all the data in the pipe and then write it all back.

To store larger amounts of data, we'll just use lots of pipes. In Linux we can store up to 1 MB per pipe, but there's a per-user limit of 64 MB total buffer size. Except that the pipe create call can never fail... it might just give you a really small pipe. Like, a 4K pipe. But each pipe uses 2 file descriptors, so this only gives us a max of 128 MB of storage. Can we do better?

Use write once pipes, which close the input file descriptor after we write. So now we can get up to 256 MB per process. Maybe let's have a lot of processes?

< Kamal demos a program that uses this trick to get 2 GB of kernel buffers using a lot of processes, but he's blocked by the total file descriptor limit on the system >

Ok, now we'll upgrade ourselves to have way more file descriptors total in the kernel

< Kamal re-runs the program; the Linux OOM killer goes crazy and his machine appears to crash. Turns out it killed his login session >
