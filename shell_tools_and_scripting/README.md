1. Lecture notes

https://missing.csail.mit.edu/2020/shell-tools/

2. Defining variable

```commandline
$ # Don't have spaces
$ foo=bar
$ echo $foo
$ bar
```

3. Single quotes or double quotes
    - Single quotes can be used as raw strings.
    - Double quotes can still replace variables.

4. Defining functions

```commandline
mcd(){
    mkdir $1
    cd $1
}
```

5. What is the use of `source` vs shebang?
    - Source runs the content of the file in the same shell.
    - shebang executes in another shell as a subprocess.
       ```commandline
       mcd(){
           mkdir $1
           cd $1
       }
       ```
    - If you want the above to execute in the same shell, do `source filename` and the function would be available in
      the same shell.

6. `$?`, `$_`, `sudo !!`, `$#`, `$$`, `$@`
   - $? - errorcode of the previous command. Ex
   ```commandline
   $ fasle
   $ echo $?
   $ 0
   ```
   - $$ - pid of the current program
   - $# - number of arguments passed to the current program
   - $@ - all the arguments passed to the function

7. short-circuiting

```commandline
$ false || echo "Always printed"
$ true || echo "Never printed"
$ true && echo "Always printed"
$ true; echo "Doesn't care"
```

8. Assiging variable based on the command execution

```commandline
foo=$(pwd)
$ # Parenthesis are used in running the code
```

9. Process substitution

```commandline
$ # <(ls) write the output of the command to a temp file and then it is concated by cat command.
$ cat <(ls) <(ls ..)
```

10. Expansion
   - `echo 123.{jpg,png}` will expand by clicking the tab to `echo 123.jpg 123.png`
   - `echo abc{1..9}/abc/{2..4}`

11. Inline diff using process substituion command
   - ```commandline
      $ diff <(ls foo) <(ls bar)
      ```