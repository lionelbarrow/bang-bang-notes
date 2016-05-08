### Tales of the Cursed Operating Systems Textbook

_Kiran Bhattaram_

1. Kernel memory leaks

Stripe started seeing sadness in internal DNS servers. Things would run out of memory and the Linux OOM killer would kill stuff... even though nothing was using that much memory. Looking at the logs, almost all memory was being used by the internal kernel slab.

They knew something was using memory in the kernel but didn't know what it was.

Enter /proc/slabinfo. Turns out a lot of anon_vmas were running around.

The bug was to form the nsd process and then kill the parent. But the pointer to the old process would leak in the kernel.

2. Networking slowness

In a pubsub section, publishing a message to localhost was taking 40 ms. How?

The HTTP library was sending a header, getting an ack, then sending the body and getting an ack. Using Nagle's algorithm, the server was buffering packets because there wasn't enough data to ack. After switching to send the body before waiting for the header to ack, everything sped up.

3. Oints

Stripe stores data in Mongo and periodically does filesystem level snapshot backups. They periodically attempt automated restoration to test the backups.

The error was something in Mongo saying "oints", which somehow indicated index correctly. This turned out to be because they were fsyncing when snapshotting but not blocking incoming writes while doing so.

4. Concurrency

This one was cutoff due to time.
