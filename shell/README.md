# Learning from first lecture

1. Lecture Notes

https://missing.csail.mit.edu/2020/course-shell/

2. Useful commands

```commandline
# Bring to home directory
cd ~
# Bring to the previous directory. Can use to toggle between two directory.
cd -
```

3. Option vs flag
    - Argument that take some value is called option and the one that does not called flag.

4. Permission model of file
    - (directory/file)(permision to onwer)(permission to group)(permission to all other user)

5. Kind of permissions
    - read, write, and execute

6. Permission on directory
    - read - list on directory
    - write - modify the content of the directory by creating a file or deleting.
    - execute - search (or can you enter the directory)

7. Stream
    - Every program has three stream. Input stream, output stream, and error stream.
    - The default input stream is keyboard.
    - The default output stream is terminal.
    - We can change the input and output stream using the angle bracket.
    - `echo hello > hello.txt`

8. Redirection of streams

```commandline
$ echo hello > hello.txt
$ cat - < hello.txt
$ cat - < hello.txt > hello2.txt
```

9. Piping
    - Pipe allows to connect two commands such that the command on the right of the pipe take the output of the command
      on the left of the pipe.
    - ```commandline
         $ curl --head --silent google.com | grep -i content-length | cut -d -f2
         $ 219 
      ```
    - The command in pipe and redirection are run by shell as the users running the shell.

10. Root

- Root is noted as `#` but user is noted by `$`.

11. Tee command
    - Copy the content of the standard input to one or more file.
    - `echo 1024 > sudo tee brightness`
    - In the above command, there is a brightness file. We want to put 1024 there but only root user has the modify
      access on the file. We can achieve this by using tee command to run it as root and let it output the data to
      brightness file.

12. How does shell finds the command to run?
    - It looks for the command in the $PATH path.
    - `pwd` - p working director

## Exercises

1. Use | and > to write the “last modified” date output by semester into a file called last-modified.txt in your home
   directory.
```commandline
 ./semester | grep -i "last-modified" | cut -d':' -f2 > ~/last-modified.txt
```