Download Link: https://assignmentchef.com/product/solved-cpe202-lab-6-basic-comparison-sorts
<br>
A comparison sort is a type of sorting algorithm that compares elements in a list (array, file, etc) using a comparison operation that determines which of two elements should occur first in the final sorted list. The operator is almost always a <strong>total order</strong>:

<ol>

 <li>a ≤ a for all a in the set</li>

 <li>if a ≤ b and b ≤ c then a ≤ c (transitivity)</li>

 <li>if a ≤ b and b ≤ a then a=b</li>

 <li>for all a and b, either a ≤ b or b ≤ a // any two items can be compared (makes it a total order)</li>

</ol>

In situations where three does not strictly hold then, it is possible that a and b are in some way different and both a ≤ b and b ≤ a; in this case either may come first in the sorted list. In a <strong>stable sort</strong>, the input order determines the sorted order in this case.

The following link shows visualization of some common sorting algorithms:

https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html

Your goal for this lab is to implement simple versions of Insertion Sort – <strong>insertion_sort(alist)</strong>, and Selection Sort – <strong>selection_sort(alist), </strong>that will sort an array of integers and <strong>count the number of comparisons</strong>.  Each function takes as input a list of integers, sorts the list counting the comparisons at the same time, <strong>and returns the number of comparisons</strong>. After the function completes, the “<strong>alist</strong>” should be sorted.

The worst-case runtime complexity is (n<sup>2</sup>) for selection and insertion sort. Why? Write out the summation that represents the number of comparisons.

<strong> </strong>

Note: There is a fundamental limit on how fast (on average) a comparison sort can be, namely

 (n*log n).




Fill out and submit via GitHub, a table similar to the table below as well as answers to the questions below.




Spring 2018                                                      Lab 6

<table width="0">

 <tbody>

  <tr>

   <td width="208"> </td>

   <td width="208"><strong>Selection Sort </strong></td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>List Size </strong></td>

   <td width="208"><strong>Comparisons </strong></td>

   <td width="208"><strong>Time (seconds) </strong></td>

  </tr>

  <tr>

   <td width="208"><strong>1,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>2,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>4,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>8,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>16,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>32,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>100,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>500,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>1,000,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>10,000,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

 </tbody>

</table>




<table width="0">

 <tbody>

  <tr>

   <td width="208"> </td>

   <td width="208"><strong>Insertion Sort </strong></td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>List Size </strong></td>

   <td width="208"><strong>Comparisons </strong></td>

   <td width="208"><strong>Time (seconds) </strong></td>

  </tr>

  <tr>

   <td width="208"><strong>1,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>2,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>4,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>8,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>16,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>32,000 (observed) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>100,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>500,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>1,000,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="208"><strong>10,000,000 (estimated) </strong></td>

   <td width="208"> </td>

   <td width="208"> </td>

  </tr>

 </tbody>

</table>




<ol>

 <li>Which sort do you think is better? Why?</li>

</ol>










<ol start="2">

 <li>Which sort is better when sorting a list that is already sorted (or mostly sorted)? Why?</li>

</ol>










<ol start="3">

 <li>You probably found that insertion sort had about half as many comparisons as selection sort. Why?  Why are the times for insertion sort not half what they are for selection sort?  (For part of the answer, think about what insertion sort has to do more of compared to selection sort.)</li>

</ol>