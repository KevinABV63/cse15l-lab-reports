### Lab Report 1

***Example 1: No argument***

[user@sahara ~/lecture1]$ `ls`  
Hello.class  Hello.java  messages  README  
The command lists all the files in the lecture1 folder.

[user@sahara ~/lecture1]$ `cd`  
There is no output, but the current directory becomes /home

[user@sahara ~/lecture1]$ `cat`  
Does not show any content because there is no file specified.

The working directory at the beginning was home/lecture1

***Example 2: Directory as argument***

[user@sahara ~/lecture1]$ `ls` messages  
en-us.txt  es-mx.txt  es-ve.txt  zh-cn.txt  
The command lists the files in the messages folder.

[user@sahara ~/lecture1]$ `cd` messages  
[user@sahara ~/lecture1/messages]$  
The current directory is the one showed above now.

[user@sahara ~/lecture1/messages]$ `cat` messages  
bash: cd: messages: No such file or directory *  
There is no folder in messages called messages.

The working directory at the beginning was home/lecture1

***Example 3: File as argument***

[user@sahara ~/lecture1]$ `ls` Hello.java
Hello.java
The command lists the file as it is because it is not a directory.

[user@sahara ~/lecture1]$ `cd` Hello.java  
bash: cd: Hello.java: Not a directory  
As the output prints, the Hello.java file is not a directory and cannot become one.

[user@sahara ~/lecture1]$ `cat` Hello.java  
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {  
  public static void main(String[] args) throws IOException {  
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);      
    System.out.println(content);  
  }  
}   
The command displays the contents of the Hello.java file.

Once again, the working directory as the beginning was home/lecture1.










