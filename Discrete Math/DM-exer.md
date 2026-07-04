# Discrete Maths Exercises
*VGU-CS study program*

## 1. Basic Counting Rules

1. How many subsets of a set with $n$ elements have exactly two elements (2-element subsets)?
2. How many subsets of a set with 100 elements have at most two elements?
3. How many subsets of a set with 100 elements have more than two elements?
4. How many subsets of a set with $n$ elements are there?
5. How many strings of five ASCII characters contain the character @ at least once (note that there are 128 different ASCII characters)?
6. How many bit strings of length 5 contain
   a. exactly two occurrences of 0s;
   b. at most two occurrences of 0s;
   c. at least two occurrences of 0s.
7. Prove that Euler's phi function $\varphi(p^k) = p^k - p^{k-1}$ where $p$ is prime and $k$ is a positive integer.
8. The chairs of an auditorium are to be labeled with an uppercase English letter followed by a positive integer not exceeding 100. What is the largest number of chairs that can be labeled differently?
9. How many different license plates can be made if each plate contains a sequence of three uppercase English letters followed by three digits (and no sequence of letters are prohibited even if they are obscene)?
10. A password for a certain computer system is supposed to be between 4 and 8 characters long and composed of lower and/or upper case letters. How many passwords are possible?
11. In how many ways may a ten person club select a president and a two person executive advisory board from among its members (assume that the president is not on the advisory board)?
12. What is the number of five digit numbers? What is the number of five digit numbers that have no two consecutive digits equal? What is the number that have at least one pair of consecutive digits equal?
13. List all functions from $[3]$ to $[2]$.
14. List all one-to-one functions from $[2]$ to $[3]$.
15. List all bijections from $[3]$ to $[3]$.
16. How many functions from $[m]$ to $[n]$ are there?
17. List all one-to-one functions from $[2]$ to the set $[4]$.
18. How many one-to-one functions from $[3]$ to $[5]$ are there?
19. How many one-to-one functions from $[m]$ to $[n]$ are there?
20. In how many ways can you draw a first card, second, and third card from a deck of 52 cards?
21. In how many ways can you draw two cards from a deck of 52 cards (the order of drawing is not important)?
22. Given $n$ different objects put in a secret box. Take $k$ objects out of the box.
    a. How many ways to do that if the order of the taking matters.
    b. How many ways to do that if the order of the taking does not matter.
23. In how many ways can we pass out $k$ distinct pieces of fruit to $n$ children with no restriction on how many pieces of fruit a child can get?
24. In how many ways can we pass out $k$ distinct pieces of fruit to $n$ children if each child may get at most one? What is the number if $k > n$? Assume for both questions that we pass out all the fruit.
25. In how many ways can we pass out $k$ identical pieces of fruit to $n$ children if each child may get at most one? What is the number if $k > n$? Assume for both questions that we pass out all the fruit.
26. How many bit strings of length $n$ have exactly $k$ occurrences of 0s?
27. A tennis club has $2n$ members. We want to pair up the members by twos for single matches. In how many ways may we pair up all the members of the club? If suppose that in addition to specifying who plays whom, for each pairing we say who serves first. Now in how many ways may we specify our pairs?
28. How many numbers of 3 digits whose digits are pairwise different and decrease from left to right?
29. Give a bijection that proves that $\binom{n}{k} = \binom{n}{n-k}$.
30. Give two proofs for the following identities:
    a. $\binom{2n}{2} = 2\binom{n}{2} + n^2$
    b. $\binom{n}{1} + 2\binom{n}{2} + 3\binom{n}{3} + \cdots + n\binom{n}{n} = n2^{n-1}$
    c. $n\binom{n-1}{2} = \binom{n}{2}(n-2)$
    d. Pascal's triangle: $C_n^k = C_{n-1}^k + C_{n-1}^{k-1}$
    e. $C_n^k C_k^j = C_n^j C_{n-j}^{k-j}$
    f. $C_n^k C_{n-k}^j = C_n^j C_{n-j}^k$
    g. Vandermonde's identity: $C_{m+n}^r = \sum_{i=0}^{r} C_m^i C_n^{r-i}$
31. How many permutations of the characters ABC12DE contain the string BC1?
32. A group contains $n$ men and $n$ women. How many ways are there to arrange these people in a row if the men and women alternate?
33. A class has 25 students. How many choices are there to pick 3 students to participate in a Calculus competition? How many choices to pick 3 students, one will participate in a Calculus competition, one will participate in an Algebra competition, and one will participate in a Discrete Math competition?
34. A class has 9 female and 20 male students. How many ways to pick 11 students for a soccer team if
    a. the team must have exactly 3 female students?
    b. the team must have at least one female student?
35. Count the number of bit strings of length 7 that either start with a 0 or end with the two bits 10.
36. The row of Pascal's triangle containing the binomial coefficients $\binom{10}{k}$, $0 \le k \le 10$, is
    $$1\ 10\ 45\ 120\ 210\ 252\ 210\ 120\ 45\ 10\ 1$$
    Use Pascal's formula to produce the two rows immediately following this row in Pascal's triangle.
37. Find the coefficient of $x^{101}y^{99}$ in the expansion of $(2x - 3y)^{200}$.
38. Give the formula for the coefficient of $x^k$ in the expansion of $\left(x + \frac{1}{x}\right)^{100}$, where $k$ is an integer.
39. Find the coefficient of $x^{101}y^{99}z^{105}$ in the expansion of $(2x - 3y - z)^{305}$.
40. If you have ten distinct chairs to paint, in how many ways could you paint three of them green, three of them blue, and four of them red?
41. **(Lattice problem)** In a Cartesian coordinate system, how many paths are there from the origin to the point with integer coordinates $(m, n)$ if the paths are built up of exactly $m+n$ horizontal and vertical line segments each of length one?
42. True or False, give the reason for your answer: $\binom{n}{k} = \binom{n-2}{k-2} + \binom{n-2}{k-1} + \binom{n-2}{k}$.
43. How many different strings can be made from the letters in CASABLANCA, using all letters?
44. How many different strings can be made from the letters in SUCCESS, using all letters?
45. Find the coefficient of the monomial $x^3y^2z^5$ in the expansion of $(2x - 3y - 2z)^{10}$.
46. How many ways are there for three identical red apples and two identical golden apples to be lined up in a line?
47. How many ways are there for three identical red apples, two identical golden apples, and four identical green apples to be lined up in a line?
48. How many ways are there to distribute $k$ indistinguishable apples to $n$ children?
49. How many ways are there to place $k$ indistinguishable books onto the $n$ shelves of a bookcase?
50. How many non-negative solutions of the equation $x_1 + x_2 + \cdots + x_n = k$ are there?
51. How many solutions to the equation $x_1 + x_2 + \cdots + x_n = k$ are there with each $x_i > 0$ and $x_i \in \mathbb{Z}$?
52. In how many ways may we pass out $k$ indistinguishable apples to $n$ children if each child must get at least one apple?
53. In how many ways may $n$ red checkers and $n+1$ black checkers be arranged in a circle?
54. How many solutions are there to the equation $x_1 + x_2 + x_3 + x_4 + x_5 = 21$, where $x_i$, $i=1,\dots,5$ are non-negative integers such that
    a. $x_i \ge 1$, for $i = 1, 2, \dots, 5$
    b. $x_i \ge 2$, for $i = 1, 2, \dots, 5$
    c. $0 \le x_1 \le 10$
55. How many solutions are there to the inequality $x_1 + x_2 + x_3 \le 11$, where $x_1, x_2, x_3$ are non-negative integers?
56. Which of the following subsets form a partition of the set of all real numbers?
    a. The subset of positive integers, the subset of negative integers
    b. The subset of non-positive integers, the subset of non-negative integers
    c. The subset of rational numbers, the subset of irrational numbers
    d. The closed intervals $[n, n+1]$ where $n$ is an integer
    e. The intervals $(n, n+1]$ where $n$ is an integer
57. List all partitions of $[4]$ into $k = 1, k=2, k=3, k=4$ parts. What is the value of $S(4,k)$? What is the value of the 4th Bell number?
58. What are $S(n,1)$, $S(n,n-1)$, $S(n,n)$ in the general case $n$?
59. Construct a recursive formula for $S(n,k)$ in the general case $n$. What is the value of $S(n,2)$?
60. Construct a bijection from the set of all partitions of $[n]$ into 2 parts to the family of non-empty subsets of $[n-1]$.
61. Which of these collections of subsets are partitions of $\{1,2,3,4,5,6\}$:
    a. $\{1,2\}, \{2,3,4\}, \{4,5,6\}$
    b. $\{1\}, \{2,3,6\}, \{4\}$
    c. $\{2,4,6\}, \{1,3,5\}$
    d. $\{1,4,5\}, \{2,6\}$
62. How many ways are there to place 4 distinct gifts into 3 identical boxes?
63. How many ways are there to place 4 distinct gifts into 3 identical boxes such that each box must contain at least one gift?
64. How many ways are there to place 4 identical gifts into 3 identical boxes?
65. How many ways are there to place 4 identical gifts into 3 identical boxes such that each box must contain at least 1 gift?
66. How many ways are there to place 15 distinct gifts into 10 distinct boxes?
67. How many ways are there to place 15 distinct gifts into 10 distinct boxes such that each box contains at least 1 gift?
68. How many ways are there to place 15 distinct gifts into 10 distinct boxes such that each box contains at most 1 gift?
69. How many ways are there to place 10 distinct gifts into 15 distinct boxes such that each box contains at most 1 gift?
70. How many ways are there to place 100 identical gifts into 3 distinct boxes?
71. How many ways are there to place 100 identical gifts into 10 distinct boxes such that each box contains at least 5 gifts?
72. Write down all possible permutations of $[4]$ that map 1 to 3.
73. Write down all possible permutations in two-line notation of $[5]$ that have 5 as one of their fixed points and that map 3 to 2.
74. Write down the following permutations in cycle notation and two-line notation; find their fixed points; the number of cycles that those permutations contain; calculate $\sigma^{-1}$ (inverse function), $\sigma^2$ in each case.
    a. $\sigma = 36215847$
    b. $\sigma = 42765813$
    c. $\sigma = 361452$
    d. $\sigma = 32156487$
75. Write down the two-line notation for each of the following permutations. Compute $\sigma^{-1}$ and $\sigma^2$:
    a. $\sigma = (1,3,5)(2,4,6)$
    b. $\sigma = (2,3)(1,7)(5)(6,2)$
    c. $\sigma = (7,5,3,1)(2,4,6)$
    d. $\sigma = (2,7)(6,5,1)(4,3)$
76. List all permutations without fixed points on $[4]$ and $[6]$.
77. List all permutations with 2 cycles of $[4]$ and of $[6]$.
78. List all derangements of $[3]$ and $[4]$. Prove that $D_n = (n-1)(D_{n-1} + D_{n-2})$.
79. Suppose that 8 men give their hats to a hat-check person. How many ways can the hats be given back to the men, each man receiving 1 hat such that no man receives his own hat?
80. A student has three mangos, two papayas, and two kiwi fruits. If the student eats one piece of fruit each day, and only the type of fruit matters, in how many different ways can these fruits be consumed?
81. There are 4 men and 6 women. Each man marries one of the women. In how many ways can this be done?
82. How many ways are there to pack eight identical DVDs into five indistinguishable boxes so that each box contains at least one DVD?
83. There are 10 questions on a discrete mathematics final exam. How many ways are there to assign scores to the problems if the sum of the scores is 100 and each question is worth at least 5 points?
84. How many permutations of $[2n]$ assign even numbers to odd numbers?
85. In a bureau drawer there are 60 socks, all identical except for their color: 10 pairs are red, 10 pairs are blue, 10 pairs are green. The socks are all mixed up in the drawer, and the room is totally dark. What is the smallest number of socks you must remove to be sure that you have at least one matching pair?
86. Prove that if 5 points are placed anywhere on or in a square of side length 1, at least two points will be no farther apart than $\frac{\sqrt{2}}{2}$.
87. Prove that if 5 points are placed anywhere on or in an equilateral triangle of side length 1, at least two points will be no farther apart than $\frac{1}{2}$.
88. Show that among any $n+1$ positive integers not exceeding $2n$ there must be an integer that divides one of the other integers.
89. Show that if seven integers are selected from the first 10 positive integers, there must be at least two pairs of these integers with the sum 11. Is the conclusion true if six integers are selected rather than seven?
90. Show that if you pick seven numbers from the set of consecutive integers from 2 to 13, then you can always find two of them whose sum is exactly 15.
91. There are 12 chairs in a row, and 9 people sitting. Prove that there are 3 consecutive chairs occupied.
92. Prove that every sequence of $n^2+1$ distinct real numbers contains a subsequence of length $n+1$ that is either strictly increasing or strictly decreasing.

---

## 2. Advanced Counting Rules

1. Find generating functions for the following sequences
   a. Consecutive non-negative integers $(1, 2, \dots, n, \dots)$
   b. The number of $k$-combinations with repetition of $[n]$, for a fixed number $n$, and $k = 0, 1, 2, \dots$
   c. Perfect square numbers $(1, 4, 9, 16, \dots)$
   d. Fibonacci numbers: $(0, 1, 1, 2, 3, 5, \dots)$
   e. Catalan numbers: $(1, 1, 2, 5, 14, 42, \dots)$
   f. The number of ways of filling a bag with $n$ fruits such that
      i. The number of apples must be even
      ii. The number of bananas must be a multiple of 5
      iii. There are at most four oranges
      iv. There is at most one pear
2. Let $A(x) = a_0 + a_1x + \cdots$ be the generating function for the sequence $(a_0, a_1, a_2, \dots)$. Express in terms of $A$ the generating functions for the following sequences:
   a. $(a_0, a_0+a_1, a_1+a_2, a_2+a_3, \dots)$
   b. $(a_1, a_2, a_3, \dots)$
   c. $(a_0+a_1, a_1+a_2, a_2+a_3, \dots)$
   d. $(a_0, 2a_1, 4a_2, 8a_3, \dots)$
   e. $(a_0, a_0+a_1, a_0+a_1+a_2, \dots)$
   f. $(a_0, a_1b, a_2b^2, a_3b^3, \dots)$, where $b$ is a constant.
   g. $(a_0, 0, a_2, 0, a_4, 0, \dots)$
   h. $(a_0, a_2, a_4, \dots)$
3. Find the generating function for the number of ways to pay $n$ dollars ($n = 0, 1, \dots$) from coins of denominations 3, 5, 7 dollars.
4. Find the generating function for the sequence $b_n$, where $b_n$ is the number of ways that $n$ identical candies can be distributed among 4 children and 1 adult so that each child receives an odd number of candies, and the adult receives 1 or 2 candies.
5. In a certain game it is possible to score 1, 2, or 4 points on each turn. Find the generating function for the number of ways to score $n$ points in a game in which
   a. there are at least two turns where 4 points are scored
   b. there is a multiple of 3 turns where 2 points are scored
6. What is the generating function for $\{a_k\}$, where $a_k$ is the number of solutions of $x_1+x_2+x_3+x_4 = k$, when $x_i$ are integers such that $x_1 \ge 3$, $1 \le x_2 \le 5$, $0 \le x_3 \le 4$, and $x_4 \ge 1$. Use this generating function to find $a_7$.
7. Using the generating function for the Fibonacci numbers, prove the following identities.
   a. $f_0 + f_1 + \cdots + f_n = f_{n+2} - 1$
   b. $f_0 + f_2 + \cdots + f_{2n} = f_{2n+1} - 1$
   c. $f_1 + f_3 + \cdots + f_{2n-1} = f_{2n}$
8. Find a closed formula for the number of $k$-combinations with repetition of $n$ elements by using the Maclaurin decomposition of its generating function.
9. Recall that the number of partitions of $[n]$ into 2 parts satisfies the following recurrence formula: $S(0,2) = S(1,2) = 0$ and for $n \ge 2$
   $$S(n,2) = S(n-1,1) + 2S(n-1,2) = 1 + 2S(n-1,2)$$
   Based on this recurrence formula, find the generating function for the number of partitions of $[n]$ into 2 parts. From that generating function, find a closed formula for this number.
10. Use the generating function method to solve the following recursions:
    a. $a_0 = 2$, $a_n = 3a_{n-1}$ for all $n \ge 1$
    b. $a_0 = 2$, $a_n = 3a_{n-1} + 1$ for all $n \ge 1$
    c. $a_0 = 1$, $a_1 = 2$, $a_n = 5a_{n-1} - 4a_{n-2}$ for all $n \ge 2$
    d. $u_0 = 2$, $u_1 = -6$, $u_{n+2} + 8u_{n+1} - 9u_n = 8 \cdot 3^{n+1}$
    e. $u_0 = 1$, $u_{n+1} - 2u_n = 4^n$
    f. Let $q_n$ be the number of words of length $n$ in the alphabet $\{a,b,c,d\}$ which contain an odd number of $b$. Show that $q_{n+1} = 4^n + 2q_n$.
11. For each of these generating functions, provide a closed formula for the sequence it determines
    a. $(3x-4)^3$
    b. $\frac{x^3}{1-3x}$
    c. $\frac{x^3+x}{1-3x}$
    d. $\frac{x^2}{(1-x)^2}$
    e. $\frac{x^2-x}{(1-x)^2}$
    f. $\frac{x^2}{(1-x)^3}$
12. Use generating functions to find the number of different ways 10 identical balloons can be given to four children if each child receives at least two balloons.
13. Use generating functions to find the number of different ways 15 identical objects can be put into 6 distinct boxes such that each box contains at least one but no more than three objects.
14. How many words are formed from all letters of the word MISSISSIPPI that
    a. does not contain four letters S consecutively.
    b. does not contain four consecutive letters S nor two consecutive letters P.
15. Use PIE to find the number of positive integers not exceeding 100 that are NOT divisible by 5 or by 7.
16. Use PIE to find the number of positive integers not exceeding 100 that are either odd or the square of an integer.
17. Find the number of positive integers not exceeding 1000 that are either the square or cube of an integer.
18. How many elements are in the union of four sets if each of the sets has 100 elements, each pair of the sets share 50 elements, each three of the sets share 25 elements, and there are 5 elements in all four sets?
19. In a survey of 270 college students, it is found that 64 students like Brussels sprouts, 94 like broccoli, 58 like cauliflower, 26 like both Brussels sprouts and broccoli, 28 like both Brussels sprouts and cauliflower, 22 like both cauliflower and broccoli, and 14 like all three vegetables. How many of the 270 students do not like any of these vegetables?
20. How many terms are there in the formula for the number of elements in the union of 5 sets given by PIE?
21. How many permutations of the 26 letters of the English alphabet do not contain any of the strings "fish", "rat", and "bird"?
22. How many non-negative integer solutions does the following equation have: $x+y+z = 13$, where $0 \le x, y, z \le 6$?
23. How many non-negative integer solutions does the following equation have: $x+y+z+t = 18$, where $0 \le x \le 4$, $0 \le y \le 7$?
24. How many surjective (onto) functions are there from a set with 7 elements to a set with 5 elements?
25. How many ways are there to distribute six different toys to three different children such that each child gets at least one toy?
26. In how many ways can eight distinct balls be distributed into three distinct urns if each urn must contain at least one ball?
27. How many derangements of $[4]$ are there? List all derangements of $[4]$.
28. A group of 8 students is assigned seats for each of two classes in the same classroom. How many ways can these seats be assigned if no student is assigned the same seat for both classes?
29. How many non-negative integers not exceeding 100 are there which are relatively prime with 100?

---

## 3. Graphs

*Rosen's textbook references:*
- 10.1: 23, 3-6, 9
- 10.2: 1-6, 16-22, 25, 34, 37-44, 46
- 10.3: 5, 7, 9, 10, 12, 18, 22-28, 39-40
- 10.4: 1-3, 7-9, 12-14, 21-23, 25, 33, 38, 42, 43

1. Investigate the existence of an Eulerian/Hamiltonian cycle on $C_n$, $W_n$, $K_n$, $K_{m,n}$, $Q_n$.
2. Propose an algorithm for finding an Eulerian circuit of a given graph. What is the complexity of that algorithm?
3. Show that a bipartite graph with an odd number of vertices does not have a Hamiltonian cycle.
4. A diagnostic message can be sent out over a computer network to perform tests over all links and in all devices. What sort of paths should be used to test
   a. all links?
   b. all devices?
5. Investigate the existence of a Hamiltonian cycle/path on graphs in Exercises 30–36 (Chapter 10.5, Rosen's textbook).
6. Investigate the existence of an Eulerian cycle/path on graphs in Exercises 13–14, 18–22 (Chapter 10.5, Rosen's textbook).
7. Construct a Gray code of $n$ contacts. (Hint: Use mathematical induction. Show how to produce a Gray code of $n$ contacts from one of $n-1$.)
8. How many faces are there in a tree of $n$ vertices?
9. Can six houses be connected to two utilities without connections crossing?
10. Are $Q_4$, $Q_5$, $Q_6$ planar?
11. Prove that if $G$ is a connected and planar graph, then $G$ has a vertex of degree not exceeding five.
12. Suppose that a connected planar graph has 20 vertices, each of degree 3. Into how many regions does a representation of this planar graph split the plane?
13. Is the Petersen graph planar?
14. Are $K_{3,4}$, $K_6$ planar?
15. Show that any connected triangle-free planar graph (i.e., it has no simple cycle of length three) has at least one vertex of degree not exceeding three.
16. Prove by induction on the number of vertices that any connected triangle-free planar graph is 4-colorable.

---

## 4. Trees

1. Given the following rooted tree (root $d$; children of $d$: $a, c, o, i$; children of $c$: $b, k, g$; children of $b$: $h, l$; children of $i$: $f$; children of $f$: $e, m, n$; children of $h$: $p, q$):
   a. Which vertex is the root?
   b. Which vertices are internal?
   c. Which vertices are leaves?
   d. Which vertices are of level 3?
   e. What is the height of the subtree with root $c$?
   f. List all descendants of the node $b$.
   g. Is the tree balanced?
   h. List all ancestors of $q$.
2. How many non-isomorphic unrooted trees are there with 3 vertices?
3. How many non-isomorphic unrooted trees are there with 4 vertices?
4. How many leaves does a full 3-ary tree with 100 vertices have?
5. Either draw a full $m$-ary tree with 84 leaves and height 3, where $m$ is a positive integer, or show that no such tree exists.
6. Does there exist a full 4-ary tree with 80 leaves?
7. Does there exist a full $m$-ary tree with height 4 and 100 leaves?
8. Suppose 1000 people enter a chess tournament. Use a rooted tree model of the tournament to determine how many games must be played to determine a champion, if a player is eliminated after one loss and games are played until only one entrant has not lost. Assume that there are no ties.
9. How many edges are there in a forest of $k$ trees and $n$ vertices?
10. Using alphabetical order, construct a binary search tree for the words in the sentence "The quick brown fox jumps over the lazy dog."
11. How many weighings of a balance scale are needed to find a lighter counterfeit coin among four coins? Describe an algorithm to find the lighter coin using this number of weighings.
12. How many weighings of a balance scale are needed to find a counterfeit coin among four coins if the counterfeit coin may be either heavier or lighter than the others?
13. Using a decision tree for classifying the IDs below given their properties:

| ID  | time | gender | area  | risk |
| --- | ---- | ------ | ----- | ---- |
| 1   | 1-2  | male   | urban | low  |
| 2   | 2-7  | male   | rural | high |
| 3   | >7   | female | rural | low  |
| 4   | 1-2  | female | rural | high |
| 5   | >7   | male   | rural | high |
| 6   | 1-2  | male   | rural | high |
| 7   | 2-7  | female | urban | low  |
| 8   | 2-7  | male   | urban | low  |

14. At the beginning of an exam, you try to predict whether each problem is easy or difficult ($D = +$ if it is difficult and $-$ if it is easy). Assume you use two observable problem attributes: the text length $L$ (1 if long, 0 otherwise) and the amount of math $M$ (1 if a lot of math, 0 otherwise). For training data, assume you have examined 12 previous problems and collected the following data:

| L   | M   | D   | Question |
| --- | --- | --- | -------- |
| 0   | 0   | −   | 1        |
| 0   | 0   | +   | 2        |
| 0   | 1   | −   | 3        |
| 0   | 1   | +   | 4        |
| 1   | 0   | −   | 5        |
| 1   | 0   | +   | 6        |
| 1   | 1   | −   | 7        |
| 1   | 1   | +   | 8        |
Draw a decision tree for classifying questions. How many decisions do you need to make to classify question 6?

15. Find the least number of comparisons needed to sort four elements and devise an algorithm that sorts these elements using this number of comparisons.
16. How many comparisons does the tournament sort use to find the second largest, the third largest, and so on, up to the $(n-1)$st largest (or second smallest) element?
17. Draw the tree whose Prüfer sequence is $(1,1,1,1,6,5)$.
18. Draw the tree whose Prüfer sequence is $(10,9,8,7,6,5,4,3)$.
19. Draw the tree whose Prüfer sequence is $(1,2,3,4,5,6,7,8)$.
20. Given the following labeled trees, determine their Prüfer codes. (Tree 1: root 1 with children 9, 5; 5 has children 2, 3, 8; 2 has child 6; 8 has child 4; 9 has child 7; 7 has child 10. Tree 2: root 2 with children 3, 8; 3 has children 4, 7, 9; 4 has child 1; 8 has children 6, 10; 6 has child 5.)
21. Determine which trees have Prüfer codes that have distinct values in all positions. How many labeled trees with $n$ vertices are there such that their Prüfer codes satisfy this property?
22. How many labeled trees with 6 vertices are there such that their degree sequence is
    a. $(5,1,1,1,1,1)$?
    b. $(4,2,1,1,1,1)$?
    c. $(3,2,2,1,1,1)$?
    d. $(2,2,2,2,1,1)$?
23. How many labeled trees with $n$ vertices are there such that the degree of the node labeled $n$ is equal to $k$?
24. How many labeled rooted trees on $n$ vertices are there? Propose a way to generate all labeled rooted trees of $n$ vertices uniformly.
25. How many labeled rooted forests on $n$ vertices with exactly $k$ components are there?
26. Find a spanning tree for each of these graphs: $K_5$, $C_5$, $K_{1,6}$, $K_{2,3}$, $Q_3$.
27. Draw all the spanning trees of $C_5$ and determine how many spanning trees $C_5$ has. Find its Laplacian and reduced Laplacian matrices. Check your result using the Matrix-Tree Theorem. How many spanning trees does $C_n$ have?
28. How many trees are there in the spanning forest of a graph?
29. How many edges must be removed to produce the spanning forest of a graph with $n$ vertices, $m$ edges, and $c$ connected components?
30. How many different spanning trees does each of these graphs have?
    a. $K_{2,2}$
    b. $C_n$
    c. $K_{1,n}$
    d. $K_{m,n}$
    e. $Q_3$
    f. $W_n$
31. Which connected simple graphs have exactly one spanning tree?
32. When must an edge of a connected simple graph be in every spanning tree for this graph?
33. Prove that if $G$ is a connected, simple graph with $n$ vertices and $G$ does not contain a simple path of length $k$, then it contains at most $(k-1)n$ edges.
34. Use the Matrix-Tree Theorem on the complete graph with $n$ vertices to reprove Cayley's Theorem.
35. Let $G$ be a graph and $v$ be a cut vertex of $G$. Assume that cutting vertex $v$ creates $k$ connected components $G_1, G_2, \dots, G_k$. Assume that the complexities of $G \setminus \bigcup_{i \ne 1} G_i, G \setminus \bigcup_{i \ne 2} G_i, \dots, G \setminus \bigcup_{i \ne k} G_i$ are $\kappa_1, \kappa_2, \dots, \kappa_k$ respectively. Using the Matrix-Tree Theorem, prove that
    $$\kappa(G) = \kappa_1 \kappa_2 \cdots \kappa_k$$
36. 11.5: 1, 8 (Rosen's textbook, chapter 11.5)
37. Devise an algorithm for constructing a maximum spanning tree of a connected weighted graph.
38. Show that there is a unique minimum spanning tree in a connected weighted graph if the weights of the edges are all different.
39. Devise an algorithm for finding the second minimum spanning tree in a connected weighted graph.
40. Suppose that all edge weights in a graph are integers in the range from 1 to $|V|$, where $|V|$ is the number of vertices of the graph. How fast can you make Kruskal's algorithm run? What if the edge weights are integers in the range from 1 to $k$, for some constant $k$?
41. Represent the expression $((x+2)^3)(y - (3+x)) - 5$ using a binary tree. Then write this expression in
    a. prefix notation;
    b. postfix notation;
    c. infix notation.
42. Represent the compound propositions $\neg(p \land q) \leftrightarrow (\neg p \lor \neg q)$ and $(\neg p \land (q \leftrightarrow \neg p)) \lor \neg q$ using ordered rooted trees. Write these expressions in
    a. prefix notation;
    b. postfix notation;
    c. infix notation.
43. What is the value of each of these prefix expressions?
    a. $-, *, 2, /, 8, 4, 3$
    b. $\uparrow, -, *, 3, 3, *, 4, 2, 5$
    c. $+, -, \uparrow, 3, 2, \uparrow, 2, 3, /, 6, -, 4, 2$
44. What is the value of each of these postfix expressions?
    a. $5, 2, 1, -, -, 3, 1, 4, +, +, *$
    b. $9, 3, /, 5, +, 7, 2, -, *$
    c. $3, 2, *, 2, \uparrow, 5, 3, -, 8, 4, /, *, -$

    Well-formed formulae in prefix notation over a set of symbols and a set of binary operators are defined recursively by these rules:
    (i) if $x$ is a symbol, then $x$ is a well-formed formula in prefix notation;
    (ii) if $X$ and $Y$ are well-formed formulae and $*$ is an operator, then $*XY$ is a well-formed formula.
45. Which of these are well-formed formulae over the symbols $\{x,y,z\}$ and the set of binary operators $\{\times, +, \circ\}$?
    a. $\times, +, +, x, y, x$
    b. $\circ, x, y, \times, x, z$
    c. $\times, \circ, x, z, \times, \times, x, y$
    d. $\times, +, \circ, x, x, \circ, x, x, x$
46. Show that any well-formed formula in prefix notation over a set of symbols and a set of binary operators contains exactly one more symbol than the number of operators.
47. Explain how to use breadth-first search to find the length of a shortest path between two vertices in an undirected graph.
48. Devise an algorithm based on breadth-first search or depth-first search that determines whether a graph has a cycle, and if so, finds one. Apply that for the given graph.
49. Devise an algorithm based on breadth-first search or depth-first search for finding the connected components of a graph.
50. Explain how breadth-first search and depth-first search can be used to determine whether a graph is bipartite. Apply that for the given graph (vertices $a$–$l$; see figure).
51. **The backtracking** algorithm is used to find a subset, if it exists, of the set of positive numbers with a given sum $M$ as follows: We start with a sum with no terms. We build up the sum by successively adding terms. An integer in the sequence is included if the sum remains less than $M$ when this integer is added to the sum. If a sum is reached such that the addition of any term is greater than $M$, backtrack by dropping the last term of the sum.

    Apply this for the set $\{27, 24, 19, 14, 11, 8\}$ with a given sum below. Draw the corresponding trees for each case.
    a. 20
    b. 41
    c. 60
52. There are 101 coins, and only one of them differs from the others (real ones) by weight. Using a balance scale, determine the counterfeit one with two weighings.
