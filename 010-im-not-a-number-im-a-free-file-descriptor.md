### I'm not a number, I'm a free file descriptor

_Andreas Fuchs_

File descriptors are numbers that point at an entry on the file descriptor state data structure in the kernel. File descriptors point at basically any input or output system - files, pipes, etc.

For example, `grep foo | some_file` opens a series of file descriptors for grep, the pipe, and some_file.

Through a process called inheritance, child process can inherit file descriptors from parents. You can also pass file descriptors around using UNIX domain sockets. UNIX domain sockets offer a serializable, guaranteed delivery way to send file descriptors from one process to another (but this obviously doesn't work across a network).

What happens if the sending process closes the file before the receiving process picks it up? The kernel keeps it open for you. Also, you can totally send UNIX domain sockets down in UNIX domain sockets. You can use this to circumvent the open file limit.

For example, make a pair of UNIX domain sockets that both connect to the same process. Then when you ned a file descriptor, you send it in one and then read it back out the other way -- basically using the domain sockets as a storage place for your file descriptor.

So imagine we do this with... another ring buffer! Using this you can have 200,000 open files. Then the OS itself can no longer open files. Since the file descriptors aren't associated with your process, `lsof` won't detect them. But this doesn't work on OSX the descriptors stored inside the inner rings are deleted - why? We suspect OSX does reference counting on sockets.

What does Linux do, then? It does a mark and sweep garbage collection on file descriptors!
