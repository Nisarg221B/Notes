access full course at : https://www.learnlinux.org.za/courses/build/fundamentals/ch04s05.html


![Filesytems, Cylinder, Inodes and Superblock Layouts](https://www.learnlinux.org.za/courses/build/images/diagram07.png)

Each disk drive in a Unix or Unix-like system can contain one or more file systems. A file system consists of a number of cylinder groups, which in turn contain inodes and data blocks.

Each file system has its characteristics described by its "super-block", which in turn describes the cylinder groups. A copy of the super-block is made in each cylinder group, to protect against losing it.

A file is uniquely identified by its inode on the filesystem where it resides. An inode is a data structure which holds information, or metadata ( file name, permissions , space consumed in bytes, date added, last modified time etc ) about a file on that filesystem. (ls -i , to get the inode of a file or directory).


A data block is simply a set block of space on the disk in which the actual contents of files are stored; often more than one block is used to hold the data for a file.

# Linux FS Hierarchy

to access the documented fs hierarchy in unix or macos 
use "man hier"

the manual or the man command is itself stored under user/share 

the binary executable files such as cp,ls,date,rm,rmdir commands etc are sotred under /bin/



![[Pasted image 20230719114742.png]]

The "/" directory is known as the root of the filesystem, or the root directory (not to be confused with the root user though).

The "/boot" directory contains all the files that Linux requires in order to bootstrap the system; this is typically just the Linux kernel and its associated driver modules.

The "/dev" directory contains all the device file nodes that the kernel and system would make use of.

The "/bin", "/sbin" and "/lib" directories contain critical binary (executable) files which are necessary to boot the system up into a usable state, as well as utilities to help repair the system should there be a problem.

The "/bin" directory contains user utilities which are fundamental to both single-user and multi-user environments. The "/sbin" directory contains system utilities.

The "/usr" directory was historically used to store "user" files, but its use has changed in time and **is now used to store files which are used during everyday running of the machine**, but which are not critical to booting the machine up. **These utilities are similarly broken up into "/usr/sbin" for system utilities, and "/usr/bin" for normal user applications.**

**The "/etc" directory contains almost all of the system configuration files. This is probably the most important directory on the system; after an installation the default system configuration files are the ones that will be modified once you start setting up the system to suit your requirements.**

The "/home" directory contains all the users data files.

The "/var" directory contains the user files that are continually changing.

     /var/         multi-purpose log, temporary, transient, and spool files
                   at/        timed command scheduling files; see at(1)
                   backups/   misc. backup files
                   db/        misc. automatically generated system-specific database files
                   log/       misc. system log files
                   mail/      user mailbox files
                   run/       system information files describing various info about system since it was booted
                    utmpx       database of current users; see utmpx(5)
                   spool/     misc. printer and mail system spooling directories
                    mqueue/     undelivered mail queue; see sendmail(8)
                   tmp/       temporary files that are kept between system reboots
                   folders/   per-user temporary files and caches
                  
The /usr directory contains the static user files.

/usr/         contains the majority of user utilities and applications

                   bin/      common utilities, programming tools, and applications
                   include/  standard C include files
                             arpa/       C include files for Internet service protocols
                             hfs/        C include files for HFS
                             machine/    machine specific C include files
                             net/        misc network C include files
                             netinet/    C include files for Internet standard protocols; see inet(4)
                             nfs/        C include files for NFS (Network File System)
                             objc/       C include files for Objective-C
                             protocols/  C include files for Berkeley service protocols
                             sys/        system C include files (kernel data structures)
                             ufs/        C include files for UFS
                   lib/      archive libraries
                   libexec/  system daemons & system utilities (executed by other programs)
                   local/    executables, libraries, etc. not included by the basic operating system
                   sbin/     system daemons & system utilities (executed by users)
                   share/    architecture-independent data files
		                             calendar/  a variety of pre-fab calendar files; see calendar(1)
		                             dict/      word lists; see look(1)
		                                        web2        words from Webster's 2nd International
		                                        words       common words
		                             man/       manual pages
		                             misc/      misc system-wide ascii text files
		                             mk/        templates for make; see make(1)
		                             skel/      example . (dot) files for new accounts
		                             zoneinfo/  timezone configuration information; see tzfile(5)

morden file system guide :
https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html#//apple_ref/doc/uid/TP40010672-CH2-SW2


### Using /var and /usr efficiently 

One of the benefits of having a /var directory which contains all the files that are changing or which are variable, and having another directory called /usr where the files are static and they are only read, would be that if you wanted to create an incredibly secure system you could in fact mount your /usr directory read-only.

This would mean that even while the OS system is up and running, no one, not even the root user is allowed to modify any files in that directory. However, because the system needs to be able to have read and write access to certain files in order to function, the /var partition would serve this purpose exclusively, allowing you to mount /usr as read-only.

So this means that you will be able to have a fully running machine doing all the things you would normally do except it will be virtually impossible for anybody to be able to place any Trojans or any other malicious binaries in your /usr directory.

Another benefit is that you can run diskless or almost diskless clients. Your /usr directory could for instance be mounted over the network from another machine. This means that you don't have to sacrifice all the disk space and instead you could rely on the network to provide your system with the needed binaries. This used to be very popular 5-10 years ago when disk space was quite a lot more expensive than it is today.

However thin-client technology, that seems to be making a comeback, could benefit quite a lot with being able to mount large applications from a remote file system that has a large amount of space, and the thin client could have no or very little disk space available. Examples of large applications are Open Office and Mozilla.


