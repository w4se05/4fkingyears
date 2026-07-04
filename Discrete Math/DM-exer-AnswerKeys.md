# Discrete Maths Exercises — Answer Keys
*VGU-CS study program*

## 1. Basic Counting Rules

1. $C(n,2)$
2. $C(100,2) + C(100,1) + C(100,0)$
3. $2^n - (C(100,2) + C(100,1) + C(100,0))$
4. $2^n$
5. $128^5 - 127^5$
6. Bit strings of length 5 containing:
   a. $C(5,2)$
   b. $C(5,2) + C(5,1) + C(5,0)$
   c. $C(5,2)+C(5,3)+C(5,4)+C(5,5)$, or equivalently $2^5 - C(5,0) - C(5,1)$
7. *(proof)*
8. $26 \cdot 100$
9. $26^3 \cdot 10^3$
10. $52^4 + 52^5 + 52^6 + 52^7 + 52^8$
11. $C(10,1) \cdot C(9,2)$
12. $9 \cdot 10^4$; $9^5$; $9 \cdot 10^4 - 9^5$
13. $(1,1,1); (1,1,2); (1,2,1); (2,1,1); (1,2,2); (2,1,2); (2,2,1); (2,2,2)$
14. *(list)*
15. *(list)*
16. $n^m$
17. *(list)*
18. $\dfrac{5!}{3!}$
19. $\dfrac{n!}{m!}$
20. $52 \cdot 51 \cdot 50$
21. $C(52,2)$
22. Given $n$ different objects put in a secret box. Take $k$ objects out:
    a. $\dfrac{n!}{k!}$
    b. $C(n,k)$
23. $n^k$
24. $\dfrac{n!}{k!}$ if $k \le n$, and $0$ otherwise
25. $C(n,k)$ if $k \le n$, and $0$ otherwise
26. $C(n,k)$
27. $\dfrac{(2n)!}{n! \, 2^{n+1}}$ ; $\dfrac{(2n)!}{2^n \, n!}$ — *(to check)*
28. $C(10,3)$
29. *(bijection)*
30. *(two proofs each)*
31. $5!$
32. $2(n!)^2$
33. $C(25,3)$; $3! \, C(25,3)$
34. a. $C(9,3) \cdot C(20,8)$
    b. $C(29,11) - C(20,11)$
35. $2^6 + 2^5 - 2^4$
36. *(compute rows)*
37. $2^{101}(-3)^{99}$
38. $C\left(100, \dfrac{100+i}{2}\right)$ if $i$ is even and $0 \le i \le 100$, and $0$ otherwise
39. $\dfrac{305!}{101! \cdot 99! \cdot 105!} \cdot 2^{101} \cdot 3^{99}$
40. $\dfrac{10!}{3! \cdot 3! \cdot 4!}$
41. $C(m+n, m)$
42. False
43. $\dfrac{10!}{2! \cdot 4!}$
44. $\dfrac{7!}{3! \cdot 2!}$
45. $-\dfrac{10!}{3! \cdot 2! \cdot 5!} \cdot 2^8 \cdot 3^2$
46. $C(5,2)$
47. $\dfrac{9!}{3! \cdot 2! \cdot 4!}$
48. $C(n+k-1, k)$
49. $C(n+k-1, k)$
50. $C(n+k-1, k)$
51. $C(k-1, k-n)$
52. $C(k-1, k-n)$
53. $\dfrac{(2n)!}{n!(n+1)!}$
54. a. $C(20,16)$
    b. $C(15,11)$
    c. $C(25,21) - C(14,10)$
55. $C(14,11)$
56. a. No
    b. No
    c. Yes
    d. No
    e. Yes
57. *(list)*
58. $1$; $C(n,2)$; $1$
59. $S(n,k) = S(n-1,k-1) + k\,S(n-1,k)$; $S(n,2) = 2^{n-1} - 1$
60. *(bijection)*
61. a. No
    b. No
    c. Yes
    d. No
62. $S(4,3) + S(4,2) + S(4,1)$
63. $S(4,3) = C(4,2)$
64. *(value)*
65. *(value)*
66. $10^{15}$
67. $S(15,10) \cdot 10!$
68. $0$
69. $\dfrac{15!}{5!}$
70. $C(102,100)$
71. $C(59,50)$
72. *(list)*
73. *(list)*
74. *(worked out)*
75. *(worked out)*
76. *(list)*
77. *(list)*
78. *(list + proof)*
79. *(value)*
80. $\dfrac{7!}{3! \cdot 2! \cdot 2!}$
81. $\dfrac{6!}{2!}$
82. *(value)*
83. $C(59,50)$
84. $(n!)^2$
85. $31$
86. *(proof)*
87. *(proof)*
88. *(proof)*
89. *(proof)*
90. *(proof)*
91. *(proof)*
92. *(proof)*

---

## 2. Advanced Counting Rules

1. a. $\dfrac{1}{(1-x)^2}$
   b. $\dfrac{1}{(1-x)^n}$
   c. $\dfrac{1+x}{(1-x)^3}$
   d. $\dfrac{x}{1-x-x^2}$
   e. $\dfrac{1-\sqrt{1-4x}}{2x}$
   f. $\dfrac{1}{(1-x)^2}$
2. a. $A(x)(x+1)$
   b. $\dfrac{A(x)-a_0}{x}$
   c. $A(x) + \dfrac{A(x)-a_0}{x}$
   d. $A(2x)$
   e. $\dfrac{A(x)}{1-x}$
   f. $A(bx)$
   g. $\dfrac{A(x)+A(-x)}{2}$
   h. $\dfrac{A(\sqrt{x})+A(-\sqrt{x})}{2}$
3. $\dfrac{1}{(1-x^3)(1-x^5)(1-x^7)}$
4. $\dfrac{x^5+x^6}{(1-x^2)^4}$
5. $\dfrac{x^8}{(1-x)(1-x^4)(1-x^6)}$
6. $\dfrac{x^5}{(1-x^5)^2 (1-x)^3}$; $a_7 = 6$
7. *(proofs using generating functions)*
8. $C(n+k-1, k)$
9. $\dfrac{x^2}{(1-x)(1-2x)}$; and $S(n,2) = 2^{n-1} - 1$
10. a. $\dfrac{2}{1-3x}$, and $a_n = 2 \cdot 3^n$
    b. $\dfrac{x+2}{1-3x}$, and $a_n = 7 \cdot 3^{n-1}$ for $n \ge 1$, $a_0 = 2$
    c. $\dfrac{1+2x}{1-5x+4x^2}$, and $a_n = \dfrac{2}{3} + \dfrac{1}{3} \cdot 4^n$
    d. $\dfrac{8+10x}{1+8x-9x^2} + \dfrac{24x^2}{(1-3x)(1+8x-9x^2)}$, and $u_n = \dots$
    e. $\dfrac{2-4x}{(1-2x)(1-4x)}$, and $u_n = 2^{n-1} + \dfrac{1}{2} \cdot 4^n$
    f. *(derivation)*
11. a. $(-64, 144, -108, 27, 0, 0, \dots)$
    b. $a_n = 3^{n-3}$ for $n \ge 3$, and $a_n = 0$ for $n = 0, 1, 2$
    c. *(value)*
    d. $a_n = n - 1$
    e. $a_n = n-1-n = -1$ for $n \ge 1$, and $a_0 = 0$
    f. *(value)*
12. *(use generating functions — see method above)*
13. *(use generating functions — see method above)*
14. *(count using PIE-style methods)*
15. *(compute using PIE)*
16. *(compute using PIE)*
17. *(compute)*
18. *(compute using PIE)*
19. *(compute using PIE)*
20. *(compute number of terms)*
21. *(compute using PIE)*
22. *(compute)*
23. *(compute)*
24. *(compute)*
25. *(compute)*
26. *(compute)*
27. *(list derangements of $[4]$)*
28. *(compute)*
29. *(compute — Euler's totient of 100)*

---

## 3. Graphs

*(No separate answer key provided in the source document — see Rosen's textbook sections 10.1–10.4 as referenced.)*

1–16. *(Answers not included in the answer key — refer to course materials / Rosen's textbook.)*

---

## 4. Trees

1. *(Answers to sub-parts a–h based on the given rooted tree — refer to figure in exercises.)*
2. *(value)*
3. *(value)*
4. *(value)*
5. *(value)*
6. *(value)*
7. *(value)*
8. *(value)*
9. *(value)*
10. *(tree diagram)*
11. *(tree diagram)*
12. *(tree diagram)*
13. *(Prüfer codes for the two given labeled trees)*
14. *(discussion)*
15. a. *(value)*
    b. *(value)*
    c. *(value)*
    d. *(value)*
16. *(value)*
17. *(value)*
18. *(value)*
19. *(spanning trees for each graph)*
20. *(spanning trees of $C_5$, Laplacian, reduced Laplacian)*
21. *(value)*
22. *(value)*
23. a–f. *(values for each graph)*
24. *(discussion)*
25. *(discussion)*
26. *(proof)*
27. *(proof via Matrix-Tree Theorem)*
28. *(proof via Matrix-Tree Theorem)*

> **Note:** The Trees section of the source answer key ends here (matching content through item 28 of Chapter 4); later exercises in the exercise sheet (e.g., prefix/postfix notation, BFS/DFS, backtracking) did not have corresponding answers in the provided answer key PDF.
