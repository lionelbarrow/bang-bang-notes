# How I fixed UNIX atime - with ten lines of code and feminism!

Valerie Aurora

Every UNIX file has three useful timestamps:
* atime - the last time the file was read or _a_ ccessed
* mtime - last time the contents were modified
* ctime - last time the metadata was changed

These are all part of the inode definition.

These timestamps are very useful. For example, sendmail can know that if atime > mtime, then no new mail has been added to the file.

Reads are often cached in memory - no SSD or disk. Writes, on the other hand, must eventually go to disk. Unfortunately atime turns almost every read into a write!

Non-feminist solution: nobody gets atime. However, this breaks a lot of programs. But if you complained about this, people would just explain to you to not use atime.

Second non-feminist solution: buffer atime writes. Lots of technical problems for this, mostly that it involves lot of random buffer updates.

Feminist solution: relative atime updates -- if the atime is already greater than mtime, don't update it. Only update atime if it's less than the mtime (or if it's greater than 24 hours old).
