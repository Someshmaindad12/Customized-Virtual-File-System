Name of the project: Customized Virtual File System

Technology used: C Programming

User interface used: Command User Interface

Platform required: As this project executes on a primary storage device, i.e., RAM, there is no special requirement for an operating system (we can use Linux / Windows / macOS).

Hardware requirements: There is no special requirement for hardware (it can execute on 512 MB storage).

Description of the project:

i) This project was developed using C programming with the goal of understanding the internals of an operating system and exploring the data structure implementation in C programming.

ii) This project is a virtual representation of a file system that provides all functionalities to the user, similar to the Linux file system.

iii) In this project, I replicated all data structures used by the operating system to manage file system-oriented tasks.

iv) As the name suggests, it is a 'Virtual File System' because it implements all records in the primary storage, i.e., RAM. Therefore, there is no special requirement for an operating system.

v) This project includes the implementations of necessary system calls and commands of a file system, including open, close, read, write, stat, fstat, among others.

vi) I created all necessary data structures required for the file subsystem, including Incore Inode Table, File Table, User File Descriptor Table, Super Block, Disk Inode List Block, and Data Block. These data structures replicate how a real operating system manages files from Hard Disk to RAM.

vii) With this project, users can access the system-level functionalities of the Linux operating system on any other operating system platform.

viii) To interact with the virtual file system, I developed a customized shell that provides a user-friendly interface for managing and manipulating files within the system.

ix) This project includes a complete layout of the file system from Hard Disk to RAM, providing a deep dive into how data is stored, managed, and accessed.

Data structures used in the project:

i) Super Block: It is a block of 1 KB size that contains information about the whole file system. This block contains information about the total number of Inodes, used Inodes, free Inodes, total number of blocks, used blocks, and free blocks.

ii) Disk Inode List Block (DILB): It is a linked list of Inodes. An Inode is considered a structure that contains information about a file. For every file, there is a separate Inode. The operating system accesses the file by considering the contents stored inside an Inode. An Inode contains the following:

 a) Inode number
 b) Name of the file
 c) Size of the file (allocated memory)
 d) Actual size of the file (size of data)
 e) Permissions of the file
 f) Last access and modification time of the file
 g) Link count
 h) Block numbers allocated to the file
iii) Data Block: The data block contains the actual data stored inside the file. Each block in the data block is 1 KB in size. Inside the data block, there is no information about the file.

iv) UAREA: UAREA is considered as the User Area. For every running process, a separate UAREA gets created. UAREA contains the UFDT in it.

v) UFDT (User File Descriptor Table): It is an array of pointers that points to entries from the file table.

vi) File Table: This table contains information about open files. It includes the offset from where we can read and write, the mode in which the file is opened, a field named count associated with new process creation, and a pointer that points to the IIT.

vii) Incore Inode Table (IIT): This table holds all the Inodes of files opened by running processes. The actual Inodes are stored in the DILB, but when a process opens a file, the Inode of that file gets loaded into RAM and is stored inside the IIT.
