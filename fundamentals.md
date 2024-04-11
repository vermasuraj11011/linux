# Fundamentals

### command, options, arguments

- **command**: The name of the command.
- **options**: Modify the behavior of the command.
- **arguments**: The input to the command.
- **syntax**: command [options] [arguments]

> **example**: ls -l /home/user
> - **ls**: command
> - **-l**: option
> - **/home/user**: argument

### Files and Permissions
- Three types of permissions: 
  > - read 
  > - write
  > - execute
- Each permission **(rwx)** can be granted to three entities:
  > - owner
  > - group
  > - others
- run **ls -l** to view file permissions
  > **rwxrwxrwx**
- command to change permissions:
  > **chmod**
````text
u for user
g for group
o for others
a for all

read = 4
write = 2
execute = 1
no permission = 0

> chmod 777 file.txt    # grant all permissions to owner, group, and others
> chmod 755 file.txt    # grant read, write, and execute permission to owner, read and execute permission to group and others
> chmod 000 file.txt    # remove all permissions from owner, group, and others
> chmod 444 file.txt    # grant read permission to owner, group, and others
> chmod g-w file.txt    # remove write permission from group
> chmod g+w file.txt    # grant write permission to group
> chmod o-r file.txt    # remove read permission from others
> chmod u+x file.txt    # grant execute permission to owner
> chmod o-r file.txt    # remove read permission from others
> chmod a-x file.txt    # remove execute permission from all
````

### File ownership
- **Owner**: The user who created the file.
- **Group**: The group the file belongs to.
- **chown**: Change the owner of a file.
- **chgrp**: Change the group of a file.
````text
> chown <user-name>:<group-group> file.txt      # change owner and group of file.txt
> chown <user-name> file.txt                    # change owner of file.txt
> chgrp <group-name> file.txt                   # change group of file.txt
````

### Access Control Lists (ACLs)
- **ACLs**: Provide more fine-grained control over file permissions.
- **getfacl**: Display the ACLs of a file.
- **setfacl**: Set the ACLs of a file.
````text
> getfacl file.txt                                      # display ACLs of file.txt
> setfacl -m u:<user-name>:<permissions> file.txt       # set ACLs for user
> setfacl -m g:<group-name>:<permissions> file.txt      # set ACLs for group
> setfacl -m o:<others>:<permissions> file.txt          # set ACLs for others
````

### Adding text to a file or redirecting output
- **echo**: Display a line of text.
- **cat**: Concatenate files and print on the standard output.
- **>**: Redirect output to a file.
- **>>**: Append output to a file.
````text
> echo "Hello, World!" > file.txt       # write text to file.txt
> cat file.txt                          # display contents of file.txt
> echo "Hello, Linux!" >> file.txt      # append text to file.txt
````

### Input and Output Redirection
- **stdin**: Standard input.
- **stdout**: Standard output.
- **stderr**: Standard error.
- **<**: Redirect input from a file.
- **>**: Redirect output to a file.
- **>>**: Append output to a file.
- **2>**: Redirect error output to a file.
- **2>&1**: Redirect error output to the same location as standard output.
````text
> cat < file.txt                # read input from file.txt
> ls > output.txt               # write output to output.txt
> ls >> output.txt              # append output to output.txt
> ls 2> error.txt               # write error output to error.txt
> ls > output.txt 2>&1          # write both output and error to output.txt
````
### Standard output to a file(tee)
- **tee**: Read from standard input and write to standard output and files.
````text
> ls | tee output.txt           # write output of ls to output.txt and display on terminal
> ls | tee -a output.txt        # append output of ls to output.txt and display on terminal
````


### Pipes and Filters
- **Pipes**: Connect the output of one command to the input of another.
- **Filters**: Modify the output of a command.
- **grep**: Search for text in files.
- **sort**: Sort lines of text files.
- **uniq**: Report or omit repeated lines.
- **wc**: Print newline, word, and byte counts for each file.
- **cut**: Remove sections from each line of files.
- **sed**: Stream editor for filtering and transforming text.
- **awk**: Pattern scanning and processing language.
````text
> ls -l | grep file.txt             # search for file.txt in the output of ls -l
> cat file.txt | sort               # sort the contents of file.txt
> cat file.txt | uniq               # remove repeated lines from file.txt
> cat file.txt | wc                 # count lines, words, and bytes in file.txt
> cat file.txt | cut -d " " -f 1    # remove sections from each line of file.txt
> cat file.txt | sed 's/old/new/g'  # replace 'old' with 'new' in file.txt
> cat file.txt | awk '{print $1}'   # print the first column of file.txt
````  


search in file
````text
> grep "pattern" file.txt           # search for 'pattern' in file.txt
> grep -i "pattern" file.txt        # search for 'pattern' case-insensitively
> grep -r "pattern" directory/      # search for 'pattern' recursively in directory
> grep -v "pattern" file.txt        # display lines that do not match 'pattern'
> grep -n "pattern" file.txt        # display line numbers of matching lines
> grep -c "pattern" file.txt        # display count of matching lines
> grep -l "pattern" file.txt        # display filenames with matching lines
> grep -w "pattern" file.txt        # search for whole words matching 'pattern'
> grep -o "pattern" file.txt        # display only the matching part of the line
> grep -E "pattern" file.txt        # use extended regular expressions
> grep -f pattern_file.txt file.txt # search for patterns from a file
````
