### Finding out what’s _really_ going on, with DTrace!

_Colin Jones_

I like it when computers work exactly what I expect. But that usually doesn't happen. It'd be nice to learn why things aren't going on.

DTrace allows you to write programs that analyze your programs. It's designed to run in production from within kernel space.

You can, for example, trace system calls. The developer can also add explicit call points for DTrace if they so choose. But the cool part is you can also trace arbitrary C function calls -- whether they're in the kernel or not!

Case study:

The team has some tests that are intermittently very slow -- usually sub second, but then pausing for 30 seconds. This is across machines! What should we check?
* GC pauses
* Connection pool contention
* Randomly forgot to delete a sleep in the code.

Using DTrace we can trace GC and find out that the slowest GC was only 160ms -- way less than 30 seconds. We also are able to rule out CPU usage. Similarly we rule out memory and disk. 

That leaves network. We use a DTrace script available online to trace network calls. As expected we have a lot of fast connections to localhost. Weirdly, though, we also call out to somewhere else - some random IP address. We use DTrace on the DNS resolver and it turns out they were all trying to connect to 'someplace.com'. Now that things are identified they were able to find a 3rd-party HTTP call in the tests, which they axed.

DTrace gets you the answers. It's not super hard -- it doesn't take years of study to get to the point where it's super useful.

To learn more read Branden Gregg's blog or "The DTrace Guide".
