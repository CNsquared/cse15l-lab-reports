
# Week Ten Lab Report
**Alex Oshima**  
**PID: A1695817**

## Comparing MarkdownParse Implementations

Looking at the differences between the results of test cases on two different markdown parse implementations

### How the Differences were found
The outputs of the test cases were outputed to a text file then those two text files were compared using diff. The output of diff was then put into a text file linked below.

[Diff Results](Files/diff.text)

### Test Case Difference #1
#### Test case 194
There was a difference in outputs on test case 194

My Implementation returned an empty list while the implementation in lab 9 provided [url]

Both implementations appear to be inncorrect because when the preview function in vscode is used the linked parsed is "my_(url)"
![Preview Results](Images/Lab-5/Screen%20Shot%202022-03-10%20at%201.59.54%20PM.png)

This means for my markdownParse it doesn't pick up anything while the implementation in lab 9 only gets the part in the ()
A potential fix for this is to take into account markdown variables. This could be done by saving a varible to an array when varible syntax is found and then checking for that variable in the text file as well


This is the section of code for the given implementation where the fix could be implemented. The code would also look for markdown variable syntax
![Code in Given](Images/Lab-5/Screen%20Shot%202022-03-17%20at%2011.02.56%20AM.png)


### Test Case Difference #2
#### Test case 201
There was a difference in outputs on test case 201

My Implementation returned an empty list while the implementation in lab 9 provided [baz]

My implementation appears to be correct because vscodes's preview shows no links
![Preview Results](Images/Lab-5/Screen%20Shot%202022-03-10%20at%204.08.10%20PM.png)

The lab 9 implementation innocorrectly pulled the text in the () as a link
A potential fix for this is to take into account the text in between the [] and () found in parse. It could find the location of [] then the nearest () and then look at the text in between, if any

This is the section of code for the given implementation where the fix could be implemented. The code would look ibetween the "]" and "("
![Code Given](Images/Lab-5/Screen%20Shot%202022-03-17%20at%2011.04.27%20AM.png)
