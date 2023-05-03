Download Link: https://assignmentchef.com/product/solved-cs1027-lab9
<br>
<h1>Learning Outcomes</h1>

<ul>

 <li>Design and implement recursive algorithms</li>

 <li>Design and implement iterative algorithms</li>

 <li>Compare iterative and recursive approaches to different methods</li>

</ul>

<h1>Pre-Lab</h1>

<ul>

 <li>Create a new Java project called Lab9</li>

 <li>Download the file: <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab09/FibonacciDemo.java">java</a></li>

 <li>Save these downloaded files into the Lab9 src folder</li>

</ul>




<h1>Exercise 1 – Iterative vs. recursive methods</h1>




<em>For some problems it is possible to design natural algorithmic solutions that are recursive and solutions that are iterative. One of these problems is that of computing the n-th Fibonacci number. The Fibonacci numbers are: 1, 1, 2, 3, 5, 8, 13, 21… </em>




<ol>

 <li>Open FibonacciDemo.java and examine the code. Carefully read through the ifib() and rfib() methods to see the iterative and recursive approaches to computing the Fibonacci numbers respectively. Why does the iterative approach require so many variables? What are the base cases of the recursive Fibonacci method?</li>

 <li>Run the program and when asked enter the number 20, 30, 40, 45, 50. Write down the running times reported by the algorithm.</li>

</ol>

<table width="53">

 <tbody>

  <tr>

   <td width="53">main()</td>

  </tr>

  <tr>

   <td width="53">rfib()</td>

  </tr>

 </tbody>

</table>

<ol start="3">

 <li>Modify the program to include a new variable called methodCalls2 that keeps track of the number of calls made to method rfib() when the value of the parameter n is 2 and prints it out in the Run the program and enter the value 40. How many calls are made to  when the value of the parameter n=2? Write down this result.</li>

 <li>Why is the recursive algorithm for computing Fibonacci numbers so slow compared to the iterative algorithm? Does the value of methodCalls2 make sense with this rationale?</li>

</ol>




<h1>Exercise 2 – More iterative vs. recursive methods</h1>




<ol>

 <li>Create a new class called Abo.java.</li>

 <li>Consider a mathematical series, Abo, defined as:

  <ul>

   <li>Abo(n) = 0 for n &lt;= 0</li>

   <li>Abo(1) = 1</li>

   <li>Abo(n) = 1 + Abo(n/2), if n &gt; 1 is even</li>

   <li>Abo(n) = 2 + Abo((n+1)/2), if n &gt; 1 is odd</li>

  </ul></li>

 <li>In the Abo class, create a method called rabo(int n) that uses recursion to calculate the value of Abo(n) for a given integer n.</li>

 <li>Add a main() method and print out the first 20 Abo numbers in the series, i.e. Abo(0) through Abo(19).</li>

</ol>

Note: the results should be: 0, 1, 2, 4, 3, 6, 5, 5, 4, 8, 7, 7, 6, 7, 6, 6, 5, 10, 9, 9

<ol start="5">

 <li>Create a method called iabo(int n) and <strong>try</strong> to calculate the series iteratively.</li>

 <li>It is not impossible to do, but it is much more complex than the recursive method. Why is this algorithm difficult to design using the iterative approach?</li>

</ol>




<h1>Exercise 3 – Permutations and Recursion</h1>




<em>Given a sequence of characters, we want to find and print all possible permutations of these characters. For example, for the sequence of characters “car”, the possible permutations are “car”, “cra”, “acr”, “arc”, “rca”, and “rac”. (Note that they don’t have to be actual words.) </em>




<ol>

 <li>Create a new class called Permutations.java.</li>

 <li>Within this class, write a recursive method called permutations(String prefix, String suffix) that receives as parameters a String prefix and a String and it prints all permutations of the characters in suffix. The prefix parameter will be empty initially and then change upon recursive calls to the method (more info below).</li>

 <li>Parameter prefix will store a permutation of several of the characters of the original string, while suffix will store the remaining (and not yet permuted) characters of the original string. Use the following hints and explanations with this method:

  <ul>

   <li>The base case is when suffix is empty. In this case prefix contains a permutation of all characters of the original string, so the algorithm must just print prefix.</li>

   <li>If suffix is not empty, then the algorithm will consider each one of the characters c of suffix and for each one of them it will do the following:</li>

   <li>remove character c from suffix to get a new string suff</li>

   <li>append c to prefix to get a new string pre</li>

   <li>invoke permutations(pre, suff)</li>

  </ul></li>

 <li>Method length() returns the length of a string, and method charAt(i) returns the character of a string at index i. To concatenate a character c to a string prefix use c+prefix. The following algorithm can be used to remove the character at index i from a string s:</li>

</ol>

private static String removeChar(String s, int i) {     return s.substring(0, i) + s.substring(i+1, s.length()); }

<ol start="5">

 <li>You also need to write a method that asks the user to enter a string, and it prints all permutations of the string’s characters by calling permutations() with that string. The initial prefix parameter will be an empty string.</li>

 <li>This is another example of a problem that would be very difficult to solve using an iterative algorithm. However, the following short recursive algorithm can be used to solve this problem.</li>

</ol>


