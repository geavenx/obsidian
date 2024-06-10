
# What are File Descriptors?

##### The beginning

The creators of UNIX, Ken Thompson and Dennis Ritchie wanted to build a system where everything is a file, cause if everything is a file, you can use the same set of operations on a wide range of resources, like network sockets or even hardware devices.

##### The actual File Descriptors
***fd***, or File Descriptors are basically a set of non-negative integers that act as handles for these type of files and resources. They are like **unique identifiers** that helps the system to interact with the services.

# Example of a fd

If you want to open a text file and read the content of it. The steps would be:
1. Opening the file: You get a fd (for this example let's take ``fd = 3``)
2. Read: Use the fd to read data.
3. Close: Use the fd to close the file.

In C programming language, would look something like this:

`int fd = open("file.txt", O_RDONLY);
`char buffer[256];
`read(fd, buffer, 256);
`close(fd);

# Why they exist?

File Descriptors serve as the communication channel between the user applications and the kernel system calls for I/O operations. They create a way to deal with the data systems.

# How to monitor fd usage in real-time?

Tools like **lsof*** or **fdisk** are useful when you want to monitor the File Descriptors usage in real-time:

- At user level
	`lsof -u <user>

- At system level
	`sudo lsof

# Standard File Descriptors

The most used are the **0, 1 and 2**:
- 0 -> stdin
- 1 -> stdout
- 2 -> stderr