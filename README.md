java c Homework 1 – Complexities and Correctness
BE205: Algorithms and Data Structures
MUST 2024 Fall ∗ Tuesday October 01 2024
1 Introduction and Review
There are several themes of this course:
• Analyzing the complexity of a given algorithm (or a snippet). • Proving the correctness or flaw of an algorithm.
• Design an algorithm for solving a given problem.
• Implement an algorithm using C++ (or C).
So, there are problems to be solved on these aspects.
∗The picture above the title, found at [1], shows some basic understanding of the big O notations.
 1

2 How to submit the homework 2.1 Mathematical notations
Math notations are needed to write the answers to Problem 1. If you do not know how to edit math equations and notations using Word, Markdown, or Latex, you may use some easy-to-understand text form in a .txt file. For example, using ^ for superscript and _ for subscript, like:
• 2n+2 is described as 2^{n+2}.
• Σni=1i2 is described as Signma_{i=1}^{n}{i^2} • Θ(n2) is described as : \Theta(n^2)
• O(n log(n) is described as: O(n*log(n))
Pictures of clear hand writing can also be accepted.
2.2
• •
• •
2.3
1.
Submission method and deadline
Submit your homework files on Moodle through the portal of Assignment 1 (you can find it on the Moodle webpage of this course).
At most three students can form a group to do the homework together. Then, only one student should submit the files through the Moodle system.
You are welcome to do the homework again. I.e., a one-person group is surely fine.
The due time is about two weeks from the date of releasing the homeowork. The exact due time for this homework should refer to the setting of Assignment 1 on Moodle.
Files to be submitted
A report file hmk1_report. You can use the proper file format you can manage (.docx, .txt, .md, .pdf ...). This file should mention
• The full names of all the group members. Or you can say you did the homework alone.
• The tasks done by each member for this homework. This part is not needed if you did the homework alone.
• Anything meaningful that you want to document, like the difficulties and errors that you solved, some summary of the experience, etc. This part could help your future work.
• Answers to Problems 1, 2, 3.
2

2. A .zip file containing all the source code files for your programs of Problem 4. It is better to prepare two folders, one for the files of Problem 4.a, and the other for Problem 4.b. Then compress the two folders into the .zip file. Make sure your program files can compile. Do not include some project files of some IDE or executable files (.o, .exe. .obj. out). Just the source code files (.h, .c, .cpp, .txt) are fine.
Some specifics: about the files to be submitted.
• The answers to Problem 1 should clearly mention the snippet number, like:
             Answer for snippet (1): ..
             Answer for snippet (2): ...
3 Problems Problem 1
If you are sure, describe the upper bound of the complexity (running time relative to the problem size n) of the following code snippets using the Θ notation; otherwise, use the O notation. When log is used, the base should be 2.
(1) int sum = 0;
for (int i = 1; i = 1; k = k / 2 )
++sum;
(8) int sum = 0;
for (int i = 0; i  a) maxSum = 0, thisSum = 0;
(int j = 0; j  maxSum) maxSum = thisSum; else if (thisSum  10 or < -11), and print the array before the rotation and after rotation.
• In this .cpp (or .c) file, besides the definition of the rotate function, describe as some comments about what is the time complexity of running this function.
Problem 4.b
We want to design some specia代 写BE205、C++
代做程序编程语言l array, call it Spin-and-Virtaul Array (SVArr), which has the following features: For the rotation task (make it ready to print its rotated elements), it can be done is a constant time (O(1)), instead of the "physical" way shown above. It is easy to know its size (the maximum number of elements can be stored in it). Out-of- boundary indexes are a not a problem. Increasing an index rotate to the right and touching the elements on the left end. Similarly, decreasing the index can rotate to the left and touch the elements on the right end. For example, given such an array arr with size 10:
⋆ arr[9 + 1] == arr[0] ⋆ arr[7 + 5] == arr[2] ⋆ arr[−1] == arr[9] ⋆ arr[23] == arr[3]
6

⋆ arr[−18] == arr[2]
It is a pain to move the elements of an array around, which are common operations in a sorting computation, specially, when an element has very large size. One idea is to have a change the "logical" indexes of the elements, instead of shuffling the of bit-sequences of array elements. For that purpose, a SV Array remembers two arrays:
• pArr, the "physical" array, the actual content of the data elements. This part does not change upon the actions like sorting or rotating.
• vArr, the "virtual-index" array, the logical indexes of the elements. This part will be updated by actions like sorting, or elements swapping.
For example, for an SVArr of 10 elements, initially, its two arrays are:
pArr 45 78 23 56 89 12 67 34 90 55 vArr 0 1 2 3 4 5 6 7 8 9
After swapping 45 and 55, then the arrays changes to :
pArr 45 78 23 56 89 12 67 34 90 55 vArr 9 1 2 3 4 5 6 7 1 0
After sorting the elements from small to large, the pArr does not change, while the vArr changes. Now, the two arrays become:
pArr 45 78 23 56 89 12 67 34 90 55 vArr 5 2 7 0 9 3 6 1 4 8
Write a program to implement SVArr, with the following requirements:
• The style of ADT (abstract data type) should be expressed. So, SVArr should be a class, with public and private members. Some .h file and .cpp files should belong to the program.
• The main function test the following features of SVArr:
– An SVArr can be built based on a common array.
– Out-of-boundary indexes can be used; Print the value of these elements.
– Rotation can be done for positive and negative amount of shifting; Print the array before and after the shifting.
• The idea of O(1) time rotation should be implemented. Print the array after some rotation to see the effects.
• Show sorting on a SVArr, its virtual indexes changes while its physical array does not change.
7

• Do not use any library tools that have already implemented or covered the features of SVArr.
• The standard features of C++ classes should be used.
• If SVArr is implemented as a C++ template class, or some equivalent features sup- porting general types of elements, you deserve some bonus points. Otherwise, you can assume SVArr contains only integers.
• C programs are also accepted.
References
[1] Buket Senturk. Time complexity. https://medium.com/@buketsenturk/time-compl exity-202eb4f1db40, 2024. Accessed: 2024-10-01.
[2] Mark Allen Weiss. Data Structures and Algorithm Analysis in C++. Person, 4th edition, 2014. https://users.cs.fiu.edu/~weiss/.
A Helpful formulas
There are several formulas helpful to solve the Problem 1. 1+1+···+1=Σn 1=Θ(log(n))
(a+0d)+(a+1d)+(a+2d)+...+(a+(n−1)d) =
􏰀n
(a+(i−1)d) = na+d
i=1
(n − 1)n 2
2
12 ni=1i
n−1 1−rn a+ar+ar2+···+an−1 =􏰀ark =a1−r =Θ(rn−1)=Θ(rn)
= Θ(n )
  k=0
n n(n+1)(2n+1)
12 + 22 + · · · + n2 = 􏰀 i2 = S = 6 = Θ(n3) i=1
 Σni=1ik = Θ(nk+1) logk(n) = Θ(log2(n))
8

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
