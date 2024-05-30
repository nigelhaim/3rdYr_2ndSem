
# File System Activity
**Submitted by:**
Lex Zedrick Lorenzo 
Nigel Haim Sebastian 

1. Consider a file system in which a file can be deleted and its disk space reclaimed while links to that file still exist. What problems may occur if a new file is created in the same storage area or with the same absolute path name? How can these problems be avoided?

	**Answer:** Let F1 represent the previous file and F2 the updated file. A user who wants to use an existing link to access F1 will actually reach F2. Observe that file F1's access protection is being used instead of file F2's.

2. The open-file table is used to maintain information about files that are currently open. Should the operating system maintain a separate table for each user or maintain just one table that contains references to files that are currently being accessed by all users? If the same file is being accessed by two different programs or users, should there be separate entries in the open-file table? Explain.

	**Answer:**  All references to the files that are being accessed should be included in a single table that the OS keeps track of. The OS is able to carry out an operation that would not be possible without maintaining a central open-file table.
	
3. What are the advantages and disadvantages of providing mandatory locks instead of advisory locks whose use is left to users’ discretion?

	**Answer:** Consistent enforcement of access policies.

4. Provide examples of applications that typically access files according to the following methods: 
	- Sequential - Applications that access files sequentially include word processors, music players, video players, and web servers.
	- Random - Applications that access files randomly include databases, video and audio editors.
5. Some systems automatically open file when it is referenced for the first time and close the file when the job terminates. Discuss the advantages and disadvantages of this scheme compared with the more traditional one, where the user has to open and close the file explicitly.
	
	**Answer:** Benefit: Less difficult for the developer. Decreased memory leaks and locking problems. One drawback is that the operating system must remember when to open and close the file. may result in several open/close processes if not sufficiently intelligent.
	
6. If the operating system knew that a certain application was going to access file data in a sequential manner, how could it exploit this information to improve performance?
	
	**Answer:** The operating system may use a method known as read-ahead caching to increase performance if it knew that a particular application would be accessing file contents in a sequential fashion.

7.  Give an example of an application that could benefit from operating system support for random access to indexed files

	 **Answer:** The operating system may use a method known as read-ahead caching to increase performance if it knew that a particular application would be accessing file contents in a sequential fashion.

8. Some systems provide file sharing by maintaining a single copy of a file. Other systems maintain several copies, one for each of the users sharing the file. Discuss the relative merits of each approach.

	**Answer:** It is not as efficient to have one shared copy of a file as it is to have multiple copies, one for each user. When multiple people are making changes to the file at once, it will become challenging. The user could not receive the correct data from the file if there is only one copy and changes are being made to it simultaneously. Additionally, using several copies—one for each user—wastes a lot of RAM.
	
9. Contrast the performance of the three techniques for allocating disk blocks (contiguous, linked, and indexed) for both sequential and random file access.

	**Answer:** All things considered, linked allocation is effective for random access but not for sequential access, contiguous allocation is efficient for both types of access, and indexed allocation is effective for both.

10. Discuss the advantages and disadvantages of supporting links to files that cross mount points (that is, the file link refers to a file that is stored in a different volume). Assume that in a particular augmentation of a remote-file-access protocol, each client maintains a name cache that caches translations from file names to corresponding file handles. What issues should we take into account in implementing the name cache?

	**Answer:** The benefit is that there is more openness in the in that the user is spared from having to remember mount positions and develop links in any situation. Nevertheless, the drawback is that the filesystem mounting the link could occur while the filesystem holding In such a case, transparent access to the file cannot be provided since the target file might not be; the error condition would reveal to the user that a link is inactive and that it does not work transcend filesystem limitations.

11. Given a mounted file system with write operations underway, and a system crash or power loss, what must be done before the file system is remounted if: 
	(a) The file system is not log-structured? 
		**Answer:** Therefore, if the file system is not log-structured, we know that a write operation is in progress and that a file was partially written, but we do not have any information about that file saved anywhere. Therefore, in order to search for discrepancies, we must scan the entire disk to determine which file was damaged during the crash.
	
	(b) The file system is log-structured?
		**Answer:** When using a log-structured file system, we can simply resume writing entries from the log onto the disk upon remounting because we have information about pending write operations in the disk log.

12. Why do operating systems mount the root file system automatically at boot time?

	**Answer:** Because it holds the necessary files for the operating system to run, the root file system is automatically mounted at boot time. It consists of files owned by the system administrator, application applications, libraries, and system configuration files.

13. Why do operating systems require file systems other than root to be mounted?

	**Answer:** Any documents or catalogs in the basic mount point index become inaccessible when you mount a record framework and remain so for the duration of the mount. The mounting system does not permanently affect these data; when unmounting the document structure, they are once again accessible. Still, mount catalogs are frequently empty because you usually don't want to contaminate already-existing data.

14. Fragmentation on a storage device can be eliminated through compaction. Typical disk devices do not have relocation or base registers (such as those used when memory is to be compacted), so how can we relocate files? Give three reasons why compacting and relocating files are often avoided.

	**Answer:** Relocation of files on secondary storage involves considerable overhead - data blocks would have to be read into main memory and written back out to their new locations. Furthermore, relocation registers apply only to sequential files, and many disk files are not sequential. For this same reason, many new files will not require contiguous disk space; even sequential files can be allocated noncontiguous blocks if links between logically sequential blocks are maintained by the disk system.

15. Discuss how performance optimizations for file systems might result in difficulties in maintaining the consistency of the systems in the event of computer crashes.

	**Answer:** The main issue that could occur is from incomplete or delayed data and metadata updates. Updates may be postponed in the hopes that the same information will be updated later or that the updated information will only last temporarily before being removed.