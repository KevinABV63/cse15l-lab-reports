# `cd`

## No arguments

```
  [user@sahara ~]$ cd
  [user@sahara ~]$ 
```

The working directory is home.

`cd` goes into a directory if it is in the current working directory. Because there was no argument, `cd` takes you back to home.

The ouput is not an error

## Directory as argument

```
  [user@sahara ~]$ cd lecture1
  [user@sahara ~/lecture1]$
```

The working directory is `home`.

`cd` goes into a directory if it is in the current working directory, so the current working directory changed to lecturel, the argument.

The ouput is not an error

## File as argument

```
  [user@sahara ~/lecture1]$ `cd` Hello.java
  bash: cd: Hello.java: Not a directory
```

The working directory is `lecturel`.

`cd` goes into a directory if it is in the current working directory, but the argument was a file so nothing happened.

The ouput is an error because it did not do what was intended.

# `ls`

## No arguments

```
  [user@sahara ~]$ ls
  lecture1
```

The working directory is `home`.

`ls` lists all the files and directories inside the current one, so all the files and directories are listed.

The output is not an error. 

## directory as argument

```
  [user@sahara ~]$ ls lecture1
  Hello.class  Hello.java  messages  README
```

The working directory is `home`.

`ls` lists all the files and directories inside the given one, so all the files and directories are inside the argument are listed. The output is not an error.

## file as argument

```
  [user@sahara ~/lecture1]$ ls Hello.java
  Hello.java
```

The working directory is `lecturel`.

`ls` prints out the name of the file in the argument.

The output is not an error.

# `cat`

## no arguments

```
  [user@sahara ~]$ cat

```
The working directory is `home`. The output does not show any content as no file was specified.

The output is not an error.

`cat` prints out whatever you type afterwards. This is because it takes the argument and prints out whatever is in it.

## directory as argument

```
  [user@sahara ~/lecture1]$ cat lecture1
  cat: lecture1: No such file or directory
```
The working directory is home. cat prints out the name of the directory in the file and that it is a directory.

The output is an error because it did not do what was intended.

## file as an argument

```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~/lecture1]$
```
The command displays the contets of the Hello.java file.

The working directory is `lecture1`. The output is not an error.







