Download Link: https://assignmentchef.com/product/solved-685-621-project1
<br>
<h1>Problem 1 – Data Analysis</h1>

The Iris Plants Database contains 3 classes of 50 instances each, where each class refers to a type of Iris plant. Five attributes/features were collected for each plant instance. It can be downloaded from <a href="https://storm.cis.fordham.edu/~gweiss/data-mining/datasets.html">iris.arff on the Sample Weka Data Sets webpage (https://storm.cis.fordham.edu/ gweiss/data</a><a href="https://storm.cis.fordham.edu/~gweiss/data-mining/datasets.html">mining/datasets.html).</a>

<ol>

 <li>Implement an algorithm to read in the Iris dataset.</li>

 <li>Implement an algorithm to visually see two sets of features and the class they belong to.</li>

 <li>Implement your sorting algorithm from Homework 1 Problem 5.</li>

</ol>

<h1>Problem 2 – Deterministic Turing Machine</h1>

In this problem you will implement two variants of a DTM. The definition and example are provided below followed by two implementations. A deterministic Turing machine consists of the following:

<ul>

 <li>A finite state control,</li>

 <li>A tape consisting of a two-way sequence of tape squares, and</li>

 <li>A read-write head.</li>

</ul>

A given DTM is manipulated through the execution of a program utilizing the following components:

<ul>

 <li>A finite set Γ of symbols,</li>

 <li>A finite set <em>Q </em>of states (<em>q</em><sub>0 </sub>is designated as the start state and <em>q<sub>Y </sub></em>and <em>q<sub>N </sub></em>are designated as halting states), where {<em>q</em><sub>0</sub><em>,q<sub>H</sub></em>} ∈ <em>Q</em>,</li>

 <li>The direction (left, right, hault) in which to move the tape head <em>s </em>∈ <em>Q</em></li>

 <li>A transition function <em>δ </em>: (<em>Q </em>− {<em>q<sub>Y </sub>,q<sub>N</sub></em>}) × Γ → <em>Q </em>× {+1<em>,</em>0<em>,</em>−1},</li>

 <li>Σ ⊂ Γ as a set of input symbols, and</li>

 <li><em>b </em>∈ Γ − Σ corresponds to the ”blank symbol” (#)</li>

</ul>

<table width="366">

 <tbody>

  <tr>

   <td width="92"><em>q</em><sub>0</sub></td>

   <td width="92">(<em>q</em><sub>0</sub><em>,</em>0<em>,</em>+1)</td>

   <td width="92">(<em>q</em><sub>0</sub><em>,</em>1<em>,</em>+1)</td>

   <td width="92">(<em>q</em><sub>1</sub><em>,b,</em>−1)</td>

  </tr>

  <tr>

   <td width="92"><em>q</em><sub>1</sub></td>

   <td width="92">(<em>q</em><sub>2</sub><em>,b,</em>−1)</td>

   <td width="92">(<em>q</em><sub>3</sub><em>,b,</em>−1)</td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

  </tr>

  <tr>

   <td width="92"><em>q</em><sub>2</sub></td>

   <td width="92">(<em>q<sub>Y </sub>,b,</em>−1)</td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

  </tr>

  <tr>

   <td width="92"><em>q</em><sub>3</sub></td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

   <td width="92">(<em>q<sub>N</sub>,b,</em>−1)</td>

  </tr>

 </tbody>

</table>

<table width="366">

 <tbody>

  <tr>

   <td width="92"><em>Q</em>−{<em>q<sub>Y </sub>,q<sub>N</sub></em>}</td>

   <td width="92">0</td>

   <td width="92">1</td>

   <td width="92"><em>b</em></td>

  </tr>

 </tbody>

</table>

This allows a DTM to be represented as a finite set of program lines with the form of a 6-tuple TM <em>M </em>= (Γ<em>,Q,s,δ,</em>Σ<em>,b</em>).

In other words, the DTM will scan the tape, and the transition function will read the symbol from Γ currently written on the table and determine what character to write in its place as well as which direction <em>s </em>to move the read-write head. Presumably, if the program indicates +1, the head moves to the right, if the program indicates −1, the head moves to the left and if the program indicates 0, the head stays still.

To see how a DTM works, suppose we have Σ ⊂ Γ as a set of input symbols and <em>b </em>∈ Γ − Σ a ”blank symbol” (#). Next suppose we have an input string <em>x </em>∈ Σ<sup>∗ </sup>where we place the symbols of <em>x </em>in consecutive cells of the tape in positions 1<em>…</em>|<em>x</em>|. All other cells on the tape are assumed to have <em>b</em>. The program will begin in state <em>q</em><sub>0 </sub>with the read-write head scanning square 1 and proceed according to the transition function.

If the current state of the DTM is ever <em>q<sub>Y </sub></em>or <em>q<sub>N</sub></em>, then the program terminates. On the other hand, if the current state is in <em>Q </em>− {<em>q<sub>Y </sub>,q<sub>N</sub></em>}, then the program continues. When transitioning, the read-write head will first erase the symbol in the square it is examining and then write the new symbol as specified by the transition function. The read-write head then either moves one position to the right or one position to the left, and the Finite State Control updates the state to some successor <em>q</em><sup>0</sup>.

Because we have limited the set of halting (or terminal) states to <em>q<sub>Y </sub>,q<sub>N</sub></em>, we note that a DTM is only able to solve problems that return a Boolean result. In particular, we say that a DMT is used to solve decision problems where <em>q<sub>Y </sub></em>indicates the DMT has decided <em>yes </em>and <em>q<sub>N </sub></em>indicates the DTM has decided <em>no</em>.

Table 1: The set of states is defined to be <em>Q </em>= <em>q</em><sub>0</sub><em>,q</em><sub>1</sub><em>,q</em><sub>2</sub><em>,q</em><sub>3</sub><em>,q<sub>Y </sub>,q<sub>N</sub></em>, and the transition function <em>δ </em>is defined by the following table

To reiterate how the DTM works, Table 1 represents the states <em>q </em>= <em>Q </em>− {<em>q<sub>Y </sub>,q<sub>N</sub></em>}, symbols in <em>x</em>, and the direction the read-write head moves (<em>s</em>). Starting with the initial state represented with <em>q</em><sub>0 </sub>the finite controller reads the initial symbol represented by <em>x</em>. At each step the controller reads the symbol <em>x </em>on the tape at state <em>q</em>, enters the state <em>q</em><sup>0 </sup>= <em>Q </em>= <em>q</em><sub>0</sub><em>,q</em><sub>1</sub><em>,q</em><sub>2</sub><em>,q</em><sub>3</sub><em>,q<sub>Y </sub>,q<sub>N</sub></em>, writes the symbol <em>x</em><sup>0 </sup>in the current cell, erasing <em>x</em>, and moves in the direction identified by <em>s</em>. This is represented as the five-tuple (<em>q,x,q</em><sup>0</sup><em>,x</em><sup>0</sup><em>,s</em>). For Table 1 the DTM is represented by the following finite-state machine in Figure 1.

0<em>,</em>1

Figure 1: DTM State Diagram

Implement the DTM example provided in the course content under Module 3 (and above). Ensure that your components as listed above are clearly identified in your variable list. The finite-state machine with the individual states, state table and five-tuple TM are shown in the above example. You should implement the following methods:

<ol>

 <li>States method, this method should have all of the operations of your TM.</li>

 <li>Program line that executes the operations for each identified state, this should follow the n-tuple TM as described above for <em>M</em>.</li>

 <li>Print method that outputs the change in tape (<em>x </em>≤ 30) after each transition function is executed.</li>

 <li>Write method, for tape larger than <em>x &gt; </em>30 write the outputs to a file</li>

</ol>