Download Link: https://assignmentchef.com/product/solved-cs-350-homework-3
<br>



(Each question, whether a top-level question or a sub-question, carries 10 marks.)

<ol>

 <li>Write a quicksort routine in Haskell which can sort any list of the following type. Ord a =&gt; [a] -&gt; [a]</li>

 <li>Write a function</li>

</ol>

uniq :: Eq a =&gt; [a] -&gt; [a]

which, given a list of elements, returns a list of unique elements.

<ol start="3">

 <li>Use higher-order functions to write a Haskell function for the following. Consider the following</li>

</ol>

<table>

 <tbody>

  <tr>

   <td width="308">~<em>a</em>00                                       <em>. .</em>~                                                                                                                                                     .~ <em>a</em>9<em>,</em>0                                      <em>…</em></td>

   <td width="299"><em>.     a</em>0<em>,</em>9~..                          ~~<em>.</em><em>a</em>9<em>,</em>9</td>

  </tr>

 </tbody>

</table>




We represent the array using some suitable data structure (e.g. a list of lists). The concrete representation of the array is not important for this question.

A position in the array is represented by a pair (<em>i, j</em>). Write a Haskell function

neighbors :: (Ord a1, Ord a2, Num a1, Num a2) =&gt;

a1 -&gt; a2 -&gt; [(a1, a2)]

which, given <em>i </em>and <em>j</em>, computes a list of positions which are immediately adjacent to (<em>i, j</em>). Note that there can be exactly 3, 5, or 8 neighbors depending on the position.

For example, neighbors 0 0

should return [(0<em>,</em>1)<em>, </em>(1<em>,</em>0)<em>, </em>(1<em>, </em>1)]. The output should be sorted ascending in lexicographic order of tuples. (You can use quicksort from Question 1 for sorting the output list.)




<ol start="4">

 <li>Using higher-order functions alone, write a Haskell function which can compute the number of words in a string. Assume that the string contains newline characters which designate the end of lines.</li>

</ol>

Hint: You may use the functions lines and words from the Haskell Prelude.

<ol start="5">

 <li>Write the function</li>

</ol>

compose_multiple :: [b -&gt; b] -&gt; b -&gt; b

which takes a list of functions, and an initial value, and performs compositions of functions in the list on the second argument. For example,

compose_multiple [succ,(x -&gt; 2*x)] 3 should return 7.

<ol start="6">

 <li>Code the following in Haskell.</li>

</ol>

<ul>

 <li>Define a data type to construct a binary tree. A binary tree is either empty, or has a root (containing a value) with two subtrees, both of which are binary trees.</li>

 <li>For the tree defined above, define a maptree f t method of the type maptree :: (a-&gt;b) -&gt; BinaryTree a -&gt; b</li>

 <li>For the tree defined above, define</li>

</ul>

foldTree :: (a -&gt; b -&gt; b -&gt; b) -&gt; b -&gt; BinaryTree a -&gt; b

which takes a ternary function <em>f</em>, an identity value, a binary tree <em>t</em>, and returns the result of the folding operation of <em>f </em>on <em>t</em>. For example,

foldTree add3 0 (Node 3 Nil (Node 2 Nil Nil)) should evaluate to 5.