Part 1

1.
Question about ```merge``` method code

Hi, I am working on the method ```merge``` for my week 7 lab, I tried the test for the method but it showed that it didn't pass ```testMerge2```. I think the bug is somewhere in the method ```merge``` but I'm not sure what exactly went wrong. Thanks!

Here's my terminal output that showed failure(my bug symptom):
![image](error1.png)

Here's my merge method:
![image](error2.png)

Here's the code for my second ```merge``` test:
![image](error3.png)

2.

Hi, double check on what the second test for ```merge``` is expecting. What output do we want if there are common letters in both lists?

3.

After seeing the response, the student noticed that when there are common letter in both lists, the letter should appear twice in the result list. Thus the student figured out that they should not increase both ```index1``` and ```index2``` when the values at these two indexes are equal, and they can combine ```<``` case with the equal case since both only require ```index2``` to increase by 1.

Student changed the code for merge to:
![image](fixed.png)

now the terminal shows:
![image](fixed2.png)

File and directory structure:
![image](structure.png)

contents of each file before fixing bug:
![image](g.png)
![image](list1.png)
![image](list2.png)
![image](test.png)
![image](bash.png)

full command line that triggered the bug:
![image](error1.png)

Description of what to edit to fix the bug:
first delete the ```else if``` statement, then change the contents inside the ```if``` statement to only increase ```index2``` instead of increasing both ```index1``` and ```index2```, these actions combined case when the lists reach values that are equal or reach values where value from ```index2``` should be put in the list as it should be sorted before the value currently from ```index1```.

Part 2

In the second half of the quarter, I learned many new things that I didn't know from lab sections, such as the command line options, the use of bash script and vim, concept of exit code, and jdb debugging. Among all these new learnings, one particular thing I learned was that we can use jdb java debugger to run the code can check value of a variable at a specific line after hitting stop set before the run command. During lecture 15 the lecture showed how to check value of s1 and s2 variables in the middle of code running to see which line generated bug.  
