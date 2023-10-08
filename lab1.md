1.cd with no argument
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
The working directory is /home

I got no change in output because no argument makes the directory change to the root directory, but the directory is already the root directory /home before change.

It's not an error.

2.ls with no argument

```
[user@sahara ~]$ ls
lecture1
```
The working directory is /home

I got lecture1 because lecture1 is the directory under the current working directory /home.

It's not an error.

3.cat with no argument

```
[user@sahara ~]$ cat
```
The working directory was /home.

I got no output because I didn't put any argument behind the command cat so it's waiting for an input.

It's not an error.

4.cd with path to directory

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```

The working directory changed from /home to /home/lecture1 after the command was run.

I got this output because now the working directory has been switched to /home/lecture1 thus I have [user@sahara ~/lecture1].

It's not an error.

5.ls with path to directory

```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  fr.txt  zh-cn.txt
```

The working directory was /home/lecture1

I got this output because the files shown in the ouput are files under the argument messages which is under the current working directory.

It's not an error.

6.cat with path to directory

```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
```

The current working directory was /home/lecture1

I got this output because cat is supposed to print the contents of files but the argument is a directory.

It's an error, cat is supposed to have arguments of files instead of directory.

7.cd with path to file

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

The working directory was /home/lecture1

I got this output because Hello.java is a file and it's not a directory, thus it cannot be an argument for cd, and an error is reported.

It's an error, cd is supposed to have arguments of directory, but Hello.java is file.

8.ls with path to file

```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```

The working directory was /home/lecture1.

I got this output because Hello.java is itself a file so there's no file or directory under it, thus the command list prints argument itself.

It's not an error.

9.cat with path to file

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
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
```

The working directory was /home/lecture1

I got this output because cat command printed the contents in the file Hello.java.

It's not an error.
