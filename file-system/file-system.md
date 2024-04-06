## Linux File System

### File System Structure

- **Root Directory**: The root directory is the top of the file system hierarchy. It is denoted by a forward slash (/).
- **/bin**: Contains binary executables.
- **/boot**: Contains the kernel and boot loader files.
- **/dev**: Contains device files.
- **/etc**: Contains system configuration files.
- **/home**: Contains user home directories.
- **/init**: Contains the initial RAM disk.
- **/lib**: Contains shared libraries.
- **/lib64**: Contains 64-bit shared libraries.
- **/libx32**: Contains 32-bit shared libraries.
- **/lost+found**: Contains recovered files after a system crash.
- **/media**: Contains mount points for removable media.
- **/mnt**: Contains mount points for temporary file systems.
- **/opt**: Contains optional software packages.
- **/proc**: Contains information about system processes.
- **/root**: The root user's home directory.
- **/run**: Contains system runtime data.
- **/sbin**: Contains system binaries.
- **/snap**: Contains snap packages.
- **/srv**: Contains service data.
- **/sys**: Contains information about the system.
- **/tmp**: Contains temporary files.
- **/usr**: Contains user binaries and libraries.
- **/var**: Contains variable data files.

### Linux File and Directory Properties

- **File Types**:
    - **Regular File**: Contains data.
    - **Directory**: Contains other files and directories.
    - **Symbolic Link**: Points to another file or directory.
    - **Block Device**: Provides buffered access to hardware devices.
    - **Character Device**: Provides unbuffered access to hardware devices.
    - **Named Pipe**: Provides inter-process communication.
    - **Socket**: Provides inter-process communication.

### File Properties

linux:/$ ls -l root
total 8

| Permissions | Links | Owner | Group | Size | Month | Day | Time  | Name                |
|-------------|-------|-------|-------|------|-------|-----|-------|---------------------|
| -rwxrwxrwx  | 1     | linux | linux | 2540 | Apr   | 3   | 18:33 | 'Google Chrome.lnk' |
| drwxrwxrwx  | 1     | linux | linux | 512  | Mar   | 16  | 00:59 | jupyter             |
| drwxrwxrwx  | 1     | linux | linux | 512  | Feb   | 1   | 21:11 | machine-learning    |
| -rwxrwxrwx  | 1     | linux | linux | 1503 | Jan   | 31  | 17:47 | meeting.txt         |
| drwxrwxrwx  | 1     | linux | linux | 512  | Apr   | 3   | 08:42 | suraj               |

This table represents the output of the `ls -l` command. The columns represent the following:

drwxrwxrwx
d -> Directory
rwx -> Read, Write, Execute
rwx -> Read, Write, Execute
rwx -> Read, Write, Execute

- **Permissions**: The file permissions for the owner, group, and others.
- **Links**: The number of hard links to the file.
- **Owner**: The owner of the file.
- **Group**: The group the file belongs to.
- **Size**: The size of the file in bytes.
- **Month**: The month the file was last modified.
- **Day**: The day of the month the file was last modified.
- **Time**: The time the file was last modified.
- **Name**: The name of the file or directory.

### File Permissions

- **r**: Read permission.
- **w**: Write permission.
- **x**: Execute permission.
- **-**: No permission.

7

### Types of Files in Linux

- **Regular File**:     (**-**) Contains data.
- **Directory**:        (**d**) Contains other files and directories.
- **Symbolic Link**:    (**l**) Points to another file or directory.
- **Block Device**:     (**b**)  Provides buffered access to hardware devices.
- **Special file or Device**: (**c**) Provides unbuffered access to hardware devices.
- **Named Pipe**: (**p**) Provides inter-process communication.
- **Socket**: (**s**) Provides inter-process communication.

### Create / Remove Files and Directories

- **touch**: Create an empty file.
- **mkdir**: Create a directory.
- **cp**: Copy files and directories.
- **mv**: Move files and directories.
- **rm**: Remove files and directories.
- **rmdir**: Remove directories.

### Find Files and Directories

- **find**: Find files and directories.
    - find . -name <filename> -type f
- **locate**: Find files and directories.
    - locate file.txt
- **which**: Find the location of a command.
- **whereis**: Find the location of a command.
- **type**: Find the location of a command.
- **file**: Determine the file type.
- **stat**: Display file status.
- **ls**: List files and directories.
- **tree**: Display directory tree.

### Wildcards

- **?**: Matches any single character.
    - List all files with the .txt extension.
  > ls ab?.txt #
- <b>*</b>: Matches zero or more characters.
    - List all files starting with the word file.
  > ls file* >

- **[ ]**: Matches any character within the brackets.
    - List all files starting with the letters a, b, or c.
  > ls [abc]*
- **{ }**: Matches any of the comma-separated patterns.
    - List files file1 and file2.
  > ls {file1,file2}
- **^**: Matches the beginning of a line.
    - List all files starting with the word file.
  > ls ^file >
- **$**: Matches the end of a line.
    - List all files ending with the word file.
  > ls file$
````text
> touch abc{1..5}.txt   # Create files abc1.txt, abc2.txt, abc3.txt, abc4.txt, and abc5.txt.
> ls abc?.txt           # List files abc1.txt, abc2.txt, abc3.txt, abc4.txt, and abc5.txt.
> ls abc[1-3].txt       # List files abc1.txt, abc2.txt, and abc3.txt.
> ls abc[!1-3].txt      # List files abc4.txt and abc5.txt.
> ls abc{1,3}.txt       # List files abc1.txt and abc3.txt.
> ls abc{1..3}.txt      # List files abc1.txt, abc2.txt, and abc3.txt.
````


### Soft Links and Hard Links

- **Soft Link**: A symbolic link that points to another file or directory.
  > ln -s source_destination
- **Hard Link**: A link that points to the same inode as the original file.
    - **ln**: Create a link to a file.
  > ln file1 file2


### File display and Manipulation
- **echo**: Display a line of text.
- **cat**: Concatenate files and print on the standard output.
- **less**: View file contents one page at a time.
- **more**: View file contents one page at a time.
- **head**: Output the first part of files.
- **tail**: Output the last part of files.
- **wc**: Print newline, word, and byte counts for each file.
- **uniq**: Report or omit repeated lines.
- **paste**: Merge lines of files.
- **tr**: Translate or delete characters.
- **gzip**: Compress files.
- **gunzip**: Uncompress files.
- **zip**: Compress files.
- **unzip**: Uncompress files.
- **df**: Report file system disk space usage.
- **du**: Estimate file space usage.
- **mount**: Mount a file system.
- **umount**: Unmount a file system.
- **ps**: Report a snapshot of the current processes.
- **top**: Display Linux processes.
- **kill**: Send a signal to a process.
- **killall**: Kill processes by name.

````text
> less file.txt                         # view file contents one page at a time
> more file.txt                         # view file contents one page at a time
> head file.txt                         # output the first part of file.txt
> tail file.txt                         # output the last part of file.txt
> wc file.txt                           # count lines, words, and bytes in file.txt
> sort file.txt                         # sort the contents of file.txt
> uniq file.txt                         # remove repeated lines from file.txt
````

### Filter and Text Processing
- **grep**: Search for text in files.
- **sort**: Sort lines of text files.
- **uniq**: Report or omit repeated lines.
- **wc**: Print newline, word, and byte counts for each file.
- **cut**: Remove sections from each line of files.
- **sed**: Stream editor for filtering and transforming text.
- **awk**: Pattern scanning and processing language.

````text
> grep "pattern" file.txt               # search for 'pattern' in file.txt
> grep -i "pattern" file.txt            # search for 'pattern' case-insensitively
> grep -r "pattern" directory/          # search for 'pattern' recursively in directory
> sort file.txt                         # sort the contents of file.txt
> uniq file.txt                         # remove repeated lines from file.txt
> wc file.txt                           # count lines, words, and bytes in file.txt
> cut -d " " -f 1 file.txt              # remove sections from each line of file.txt
> sed 's/old/new/g' file.txt            # replace 'old' with 'new' in file.txt
> awk '{print $1}' file.txt             # print the first column of file.txt
````

### File Compression and Archiving
- **tar**: Tape archive.
    - **c**: Create a new archive.
    - **x**: Extract files from an archive.
    - **t**: List the contents of an archive.
    - **z**: Compress the archive with gzip.
    - **j**: Compress the archive with bzip2.
    - **v**: Verbose output.
    - **f**: Specify the archive file.
````text
  > tar -czvf archive.tar.gz file1 file2
  > tar -xzvf archive.tar.gz
  > tar -tvf archive.tar.gz
  > tar -cjvf archive.tar.bz2 file1 file2
  > tar -xjvf archive.tar.bz2 
  > tar -tvf archive.tar.bz2
  > tar -cvf archive.tar file1 file2
````
  