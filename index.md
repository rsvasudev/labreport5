# Lab Report 5

## Part 1

Design a debugging scenario, and write your report as a conversation on EdStem. It should have:

The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. 
(Don’t actually make the post! Just write the content that would go in such a post)
A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug
You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. 
Describing the bug should involve reading some output at the terminal resulting from running one or more commands. 
Design an error that produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! 
Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.

### Original Post

#### Title : Bug Problems
##### Category: General 
Heyyyyy I've been having this problem with my code. Please help me I don't know what to do :).This is my symptom when I run ```bash test.sh```. I'm confused as the test is passing once but not the other time. 
![Image](actualsymptom)
My guess of what it might be is to do with is to do with the order the elements are merging. I've also attached relevant code
![Image](initialtest)
![Image](initialcode)

### TA Response

#### Title : Re: Bug Problems 
#### Category : General
Hi, I would try to take a look at the if statement. Are you sure it's sorting the elements in the correct way you want it to? 

Perhaps try this link:
https://www.geeksforgeeks.org/java-program-to-sort-names-in-an-alphabetical-order/

### Student response

#### Title: Re: Bug Problems 
#### Category : General
Thank you i got it to work. This is the code i changed and the output. I kept the tests the same because they were ok. The compareTo() fucntion you recommended really helped. 
![Image](codechange)
![Image](testfinished)

The bug was to do with the fact i was sorting the strings according to length rather than alphabetical order like compareTo does. The link really helped. Therefore, the merge doesn't work as the elements are put in the wrong places. The first test passed,which was rather interesting; this means that my method was working sometimes buit no all the time. As I discovered, my merge fucntion only worked because all the elements in l2 were in front of "x" and "y" in the alphabet. Thus, it sorted the elements correctly by luck!

For example, in the testmerge2() test which is failing. "c" is added to the empty arraylist before "a" is added as the length of "a" isn't smaller than the length of "c", meaning the else statement code is run in the first while loop when "a" should be added instead. In the same way, due to the nature of the if statement in the while loop, "d" and "e" are added to the empty new arraylist before "a" and any element in l1 is added. Once l2 is emptied in the first while loop, the elements in l1 are added in the second while loop. This results in an output of ```{"c", "d", "e", "a", "b", "c"}``` which is different to the expected output of ```{"a", "b", "c", "c", "d", "e"}```. Thus, there was a bug and the test fails.


### Setup Information 
Files Needed:
ListExamples.java
ListExamplesTests.java
test.sh

#### Contents















