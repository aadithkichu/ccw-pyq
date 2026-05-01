## CST 306 - Algorithm Analysis and Design (S6 CSE)

### Module V: Introduction to Complexity Theory

**Module Syllabus Overview**
This module covers the following key concepts:
* Tractable and Intractable Problems.
* Complexity Classes including P, NP, NP-Hard, and NP-Complete.
* NP Completeness proofs for the Clique Problem and Vertex Cover Problem.
* Approximation algorithms (Bin Packing, Graph Coloring).
* Randomized Algorithms, including definitions of Monte Carlo and Las Vegas algorithms, as well as the randomized version of Quick Sort with analysis.

---

### 1. Classification of Problems
In computer science, computational problems can be broadly categorized into two main types:
* **Solvable Problems:** These are further divided based on their time complexity into Tractable Problems and Intractable Problems.
* **Unsolvable Problems**

---

### 2. Tractable Problems
* **Definition:** A problem is considered tractable when its time complexity can be expressed as a polynomial function of its input size.
* **Practicality:** Because they have polynomial time complexity, solutions to tractable problems are practical and frequently implemented in real-world applications.
* **Cook-Karp Thesis:** According to this thesis, any problem that falls within the "P" complexity class is called tractable, while problems outside of P are considered intractable.

**Example: The PATH Problem**
* **Problem Statement:** Given a directed graph G, determine whether a directed path exists from a starting vertex $s$ to a destination vertex $t$.
* **Time Complexity:** $O(n)$.
* **Note:** $n$ represents the total number of vertices in the graph.

---

### 3. Intractable Problems
* **Definition:** A problem is intractable when its time complexity is expressed as an exponential function of the input size.
* **Growth Rate:** Intractable problems have a much faster rate of complexity growth compared to tractable problems, making them impractical to solve optimally for large inputs.

**Examples:**
* **Knapsack Problem:** Has a time complexity of $O(2^n)$.
* **Traveling Salesman Problem:** Has a time complexity of $O(n^2 2^n)$.

---

### 4. Deterministic vs. Non-Deterministic Algorithms
* **Deterministic Algorithms:** An algorithm is deterministic if each and every step is clear, predictable, and completely unambiguous. Given a specific input, it will always follow the exact same sequence of steps.
* **Non-Deterministic Algorithms:** An algorithm is considered non-deterministic if a few steps within the algorithm are not well-defined.

## CST 306 - Algorithm Analysis and Design (S6 CSE)

### Module V: Complexity Classes

---

### 1. Class P

* **Definition:** Class P consists of problems that can be solved in polynomial time.
* **Time Complexity:** P problems can be solved in $O(n^k)$ time, where $n$ is the input size and $k$ is a constant.

**Example 1: PATH Problem**
* **Problem Statement:** Given a directed graph $G$, determine whether a directed path exists from node $s$ to node $t$.
* **Algorithm Inputs:** $\langle G, s, t \rangle$ where $G$ is a directed graph, and $s$ and $t$ are two nodes.
* **Algorithm Steps:**
    1. Place a mark on node $s$ and enqueue it into an empty queue.
    2. Repeat step 3 until the queue is empty.
    3. Dequeue the front element $a$. Mark all unvisited neighbors of $a$ and enqueue those into the queue.
    4. If $t$ is marked, then accept. Otherwise, reject.
* **Complexity Calculation:**
    * Steps 1 and 4 will execute exactly once.
    * Steps 3 and 4 will execute at most $n$ times, where $n$ is the number of nodes in graph $G$.
    * The overall time complexity is $O(n)$.
    * Because it runs in $O(n)$ time, this is a polynomial-time algorithm.

**Other Examples of Class P Problems:**
* Single Source Shortest Path problem utilizing Dijkstra's Greedy method.
* Multistage Graph problem implemented with forward or backward dynamic programming.
* Minimum cost spanning tree using Prim's or Kruskal's method.
* Network flow problem using the Ford-Fulkerson algorithm.

---

### 2. Class NP

* **Definition:** NP (Nondeterministic Polynomial time) is a class of problems that only have non-polynomial time algorithms (like exponential or factorial time) for finding a solution, but possess a polynomial-time verifier.
* This means while we cannot find the solution quickly, we can verify a given solution in polynomial time.

**Example 1: Hamiltonian Path (HAMPATH) Problem**
* **Definition:** A Hamiltonian path in a directed graph $G$ is a directed path that goes through each node exactly once.
* **The Problem:** There is no known polynomial solution to find the Hamiltonian path from $s$ to $t$ in a given graph. The HAMPATH problem tests whether a graph contains a Hamiltonian path connecting two specified nodes.
* **Polynomial Verifiability:** Verifying the existence of a Hamiltonian path is much easier than determining its existence.

**HAMPATH Verifier Algorithm:**
* **Inputs:** $G$ (the graph), $s, t$ (two vertices), and $P$ (the path $P_1, P_2, \dots, P_m$ where $m$ is the number of nodes in the graph).
* **Steps:**
    1. Check whether $s = P_1$ and $t = P_m$. If either fails, reject.
    2. Check for the repetition of nodes in the list $P$. If any are found, reject.
    3. For each $i$ (varying from 1 to $m-1$), check whether $(P_i, P_{i+1})$ is an edge in $G$. If any are not, reject.
    4. If all tests have been passed, then accept it.
* **Conclusion:** This verification algorithm runs in polynomial time, proving that the HAMPATH problem is an NP problem.

**Example 2: CLIQUE Problem**
* **Definition:** A clique in an undirected graph is a sub-graph where every two nodes are connected by an edge. A $k$-clique is a clique containing $k$ nodes.
* **The Problem:** To determine whether a graph contains a clique of a specified size.
* **Verification:** There is no polynomial-time algorithm for this problem, but it can be verified in polynomial time.

**CLIQUE Verifier Algorithm:**
* **Inputs:** $G$ (the graph with $V$ set of vertices and $E$ set of edges), $k$ (size of clique), and $V'$ (sub-graph vertex set).
* **Steps:**
    1. Test whether $V'$ is a set of $k$ vertices in graph $G$.
    2. Check whether for each pair $(u,v) \in V'$, the edge $(u,v)$ belongs to $E$.
    3. If both steps pass, then accept. Otherwise, reject.
* **Conclusion:** This algorithm executes in polynomial time, making the CLIQUE problem an NP problem.

**Other Examples of NP Problems:**
* CIRCUIT-SAT problem
* 3CNF-SAT problem
* Vertex cover problem
* Independence set problem
* Traveling Salesman problem
* 3-coloring problem

> **Note:** Whether $P=NP$ remains one of the greatest unsolvable problems in theoretical computer science.

---

### 3. Class NP-Hard

**Polynomial Time Reductions:**

![alt text](image-54.png)

* Consider a decision problem A, which one would like to solve in polynomial time.
* Consider another decision problem B, which already has a polynomial-time algorithm.
* A procedure that transforms any instance $\alpha$ of problem A into some instance $\beta$ of problem B is called a polynomial-time reduction if it has two characteristics:
    1. The transformation takes polynomial time.
    2. The answers are the same (i.e., the answer for $\alpha$ is "yes" if and only if the answer for $\beta$ is also "yes").

* **NP-Hard Definition:** A decision problem $X$ is NP-Hard if every problem in NP is polynomial-time reducible to $X$ (denoted as $Y \le_p X$ for every $Y$ in NP).
* **Significance:** This means that $X$ is as hard as all problems in NP. If an NP-Hard problem $X$ can be solved in polynomial time, then all problems in NP can also be solved in polynomial time.

---

### 4. Class NP-Complete

* **Definition:** If a problem is in class NP as well as class NP-Hard, then that problem is NP-Complete.

**Key Examples:**
* **CIRCUIT-SAT problem:** Given a Boolean circuit $C$, is there an assignment to the variables that causes the circuit to output 1?
* **SAT (Satisfiability) problem:** Given a Boolean expression, is there an assignment to the variables that causes the expression to output 1?
* **3-CNF-SAT Problem:**
    * **Literal:** The variables and their negation in a Boolean formula.
    * **Clause:** The OR of one or more literals (e.g., $(x_1 \vee \neg x_2 \vee x_3)$).
    * **Conjunctive Normal Form (CNF):** The AND of clauses (e.g., $(x_1 \vee \neg x_2 \vee x_3) \wedge (x_1 \vee x_2) \wedge (\neg x_1 \vee x_2 \vee x_3)$).
    * **3-CNF:** Each clause has exactly 3 distinct literals.
    * **Problem Statement:** Given a 3-CNF expression, is there an assignment to the variables that causes the expression to output 1?
* **CLIQUE problem:** Given a graph $G(V, E)$ and an integer $k$, determine if the graph contains a clique of size $k$.
* **VERTEX COVER problem:** Find the set of vertices that covers all the edges of the given graph.

**NP-Completeness Proof Steps:**
To prove that a given problem is NP-Complete, you must follow these steps:
1.  **Prove that the given problem is NP:** Do this by writing a polynomial-time verification algorithm.
2.  **Prove that the given problem is NP-Hard:** Do this by writing a polynomial-time reduction algorithm from any known NP problem to the given problem.

### 1. CLIQUE Problem is NP-Complete

**Step 1: Verification Algorithm (Proving CLIQUE is in NP)**
* Write a polynomial-time verification algorithm to prove the problem is NP.
* Let $G=(V,E)$ and use the set $V' \subseteq V$ of $k$ vertices in the clique as a certificate for $G$.
* First, test whether $V'$ is a set of $k$ vertices in the graph $G$.
* Next, check whether for each pair $(u,v) \in V'$, the edge $(u,v)$ belongs to $E$.
* If both conditions are met, accept the solution; otherwise, reject it.
* Because this algorithm executes in polynomial time, the CLIQUE problem is classified as an NP problem.

**Step 2: Reduction Algorithm (Proving CLIQUE is NP-Hard)**
* Write a polynomial-time reduction algorithm from the 3-CNF-SAT problem to the CLIQUE problem (3-CNF-SAT $\le_p$ CLIQUE).
* Let $\Phi = C_1 \wedge C_2 \dots \wedge C_k$ be a Boolean formula in 3CNF with $k$ clauses.
* Each clause $C_r$ contains exactly three distinct literals: $l_1^r, l_2^r, l_3^r$.
* Construct a graph $G$ such that $\Phi$ is satisfiable if and only if $G$ has a clique of size $k$.
* For each clause $C_r = (l_1^r \vee l_2^r \vee l_3^r)$ in $\Phi$, place a triple of vertices $V_1^r, V_2^r$, and $V_3^r$ into $V$.
* Add an edge between $V_i^r$ and $V_i^s$ if they are in different triples (meaning $r \neq s$) and $l_i^r$ is not a negation of $l_i^s$.
* If $G$ has a clique of size $k$ (for instance, $k=3$), then $\Phi$ has a satisfying assignment.
* Since $G$ can easily be constructed from $\Phi$ in polynomial time, the CLIQUE problem is NP-Hard.

**Conclusion:** The CLIQUE problem is both NP and NP-Hard, making it NP-Complete.

---

### 2. Vertex Cover Problem is NP-Complete

**Definition**
* A vertex cover of a graph is a subset of its vertices where, for every edge in the graph from vertex $u$ to $v$, at least one of them must be part of the vertex cover set.
* The problem aims to find the minimum-sized vertex cover of a given graph.

**Step 1: Verification Algorithm**
* Inputs are given as $\langle G, k, V' \rangle$.
* Set a variable `count = 0`.
* For each vertex $v$ in $V'$, remove all adjacent edges from set $E$ and increment `count` by 1.
* If `count == k` and $E$ is empty, the solution is correct.
* Otherwise, the given solution is wrong.
* This executes in polynomial time, proving VERTEX COVER is an NP problem.

**Step 2: Reduction Algorithm**
* Write a polynomial-time reduction algorithm from the CLIQUE problem to the VERTEX COVER problem.
* Inputs are $\langle G=(V,E), k \rangle$.
* Construct a new graph $G'$, which represents the complement of Graph $G$.
* If $G'$ has a vertex cover of size $|V|-k$, then $G$ has a clique of size $k$.
* This reduction algorithm is a polynomial-time algorithm, making the problem NP-Hard.

**Conclusion:** The VERTEX COVER problem is both NP and NP-Hard, so it is NP-Complete.

---

### 3. Traveling Salesman Problem (TSP) is NP-Complete

**Definition**
* A salesman wishes to make a tour, visiting each city exactly once and returning to the starting city.
* Given $c(i,j)$ as the cost to travel from city $i$ to city $j$, the objective is to make a tour with the minimum total cost.

**Step 1: Verification Algorithm**
* Inputs are $\langle G, P, k \rangle$ where $P$ represents the TSP path ($P_1, P_2, \dots, P_n$) and $k$ is the maximum tour cost.
* Test whether the path $P$ contains each vertex exactly once.
* For each $i$ between 1 and $n-1$, check if $(P_i, P_{i+1})$ is an edge of $G$.
* Check whether $(P_n, P_1)$ is an edge of $G$.
* Sum the edge costs and verify if the total is at most $k$.
* Accept if all steps pass; otherwise, reject.
* This operates in polynomial time, proving TSP is an NP problem.

**Step 2: Reduction Algorithm**
* Write a polynomial-time reduction algorithm from the VERTEX-COVER problem to the TSP problem.
* Let $G=(V,E)$ be an instance of HAM-CYCLE.
* Construct an instance of TSP by building a complete graph $G'=(V,E')$.
* Define the cost function $c$ for $G'$: $c(i,j)=0$ if $(i,j)$ is an edge in $E$, and $c(i,j)=1$ if $(i,j)$ is not an edge in $E$.
* The resulting instance of TSP is $(G', c, 0)$.
* The graph $G$ has a Hamiltonian cycle if and only if graph $G'$ has a tour of cost at most 0.
* Converting the instance of VERTEX-COVER to an instance of TSP takes polynomial time, proving TSP is NP-Hard.

**Conclusion:** The TSP problem is NP and NP-Hard, making it NP-Complete.

---

### 4. Approximation Algorithms

**Concepts**
* **Approximate Solution:** A feasible solution with a value close to the optimal solution's value.
* **Approximation Algorithm:** An algorithm designed to return a near-optimal solution.
* Approximation algorithms have two primary properties: they run in polynomial time, and they produce solutions close to the optimal ones.
* They are utilized to provide approximate solutions for NP-complete optimization problems and to give fast approximations to polynomial-time problems.

**Approximation Ratio (Factor)**
* Let $C$ represent the result obtained by the algorithm and $C^*$ represent the optimal result.
* The approximation ratio evaluates the relationship between the algorithm's result and the optimal result.
* For a maximization problem ($0 < C < C^*$), the Approximation Ratio is $C^* / C$.
* For a minimization problem ($0 < C^* \le C$), the Approximation Ratio is $C / C^*$.
* The approximation ratio of an algorithm is never less than 1.
* This ratio is inversely proportional to both computational time and the overall quality of the result.
* **$k$-Approximation Algorithm:** An algorithm that carries an approximation ratio of $k$. A 1-approximation algorithm represents an optimal solution.

## CST 306 - Algorithm Analysis and Design (S6 CSE)

### Module V: Approximation Algorithms

---

### 1. Introduction to Approximation Algorithms
An approximation algorithm with a large approximation ratio may return a solution that is much worse than optimal.

**Types of Approximation Algorithms**
* **Absolute Approximation Algorithm:** An algorithm is an absolute approximation algorithm if and only if $|C^{*}-C|\le k$ for some constant $k$.
* **f(n)-Approximation Algorithm:** An algorithm is an f(n)-approximation algorithm if and only if $\frac{|C^{*}-C|}{|C^{*}|} \le f(n)$ for $C^{*}>0$.
* **c-Approximation Algorithm:** An e-approximation algorithm is an f(n)-approximation algorithm for which $f(n)\le\epsilon$ for some constant $e$.

**Examples of Approximation Algorithms**
* Bin Packing Algorithm
* Graph Coloring Algorithm

---

### 2. Bin Packing Algorithm
* **Problem Statement:** Given $n$ items of different weights and bins each of capacity $c$, assign each item to a bin such that the total number of used bins is minimized.
* **Assumption:** It is assumed that all items have weights smaller than the bin capacity.
* **Lower Bound:** The minimum number of bins required is calculated as:
  $$\text{Min no. of bins} \ge \text{Ceil} \left(\frac{\text{Total Weight}}{\text{Bin Capacity}}\right)$$

**Applications of Bin Packing**
* Loading of containers like trucks.
* Placing data on multiple disks.
* Job scheduling.
* Packing advertisements in fixed-length radio/TV station breaks.
* Storing a large collection of music onto tapes/CDs, etc.

---

### 3. Categories of Bin Packing Algorithms

**A. Online Algorithms**
* **Definition:** These algorithms are for bin packing problems where items arrive one at a time in an unknown order. Each item must be put in a bin before the algorithm considers the next item.
* **Examples:** Next Fit, First Fit, Best Fit, and Worst Fit algorithms.

**B. Offline Algorithms**
* **Definition:** In the offline version of bin packing, the algorithm can see all the items before it starts to place them into bins.
* **Examples:** First Fit Decreasing and Best Fit Decreasing algorithms.

---

### 4. Detailed Bin Packing Algorithms & Time Complexities

**Next Fit Algorithm**
* **Logic:** If the current item fits in the same bin as the last item, insert it in the same bin; otherwise, use a new bin.
* **Time Complexity:**
    * Best case: $\theta(n)$
    * Average case: $\theta(n)$
    * Worst case: $\theta(n)$

**First Fit Algorithm**
* **Logic:** Scan the previous bins in order and find the first bin where the item fits. If such a bin exists, place the item in that bin; otherwise, use a new bin.
* **Time Complexity:**
    * Best case: $\theta(n \log n)$
    * Average case: $\theta(n^{2})$
    * Worst case: $\theta(n^{2})$

**Best Fit Algorithm**
* **Logic:** Scan the previous bins and find a bin that has the minimum remaining capacity that can still accommodate the item. If such a bin exists, place the item in that bin; otherwise, use a new bin.
* **Time Complexity:**
    * Best case: $\theta(n \log n)$
    * Average case: $\theta(n^{2})$
    * Worst case: $\theta(n^{2})$

**Worst Fit Algorithm**
* **Logic:** Scan the previous bins and find a bin that has the maximum remaining capacity that can accommodate the item. If such a bin exists, place the item in that bin; otherwise, use a new bin.
* **Time Complexity:**
    * Best case: $\theta(n \log n)$
    * Average case: $\theta(n^{2})$
    * Worst case: $\theta(n^{2})$

**First Fit Decreasing Algorithm**
* **Logic:** First, sort the items in descending order of their size. Then, apply the First Fit algorithm.
* **Time Complexity:**
    * Best case: $\theta(n \log n)$
    * Average case: $\theta(n^{2})$
    * Worst case: $\theta(n^{2})$

**Best Fit Decreasing Algorithm**
* **Logic:** First, sort the items in descending order of their size. Then, apply the Best Fit algorithm.
* **Time Complexity:**
    * Best case: $\theta(n \log n)$
    * Average case: $\theta(n^{2})$
    * Worst case: $\theta(n^{2})$

---

### 5. Example Problem: Bin Packing

**Problem:** Apply different approximation algorithms on the following items with a bin capacity of 10.
* **Items:** {5, 7, 5, 2, 4, 2, 5, 1, 6}

**Lower Bound Calculation:**
* Minimum number of bins $\ge$ Ceil((Total Weight) / (Bin Capacity))
* Ceil(37 / 10) = 4

**Results by Algorithm:**
* **Next Fit:** Requires 6 bins.
* **First Fit:** Requires 5 bins.
* **Best Fit:** Requires 5 bins.
* **Worst Fit:** Requires 5 bins.
* **First Fit Decreasing:** Items are sorted to {7, 6, 5, 5, 5, 4, 2, 2, 1}. Requires 4 bins.
* **Best Fit Decreasing:** Items are sorted to {7, 6, 5, 5, 5, 4, 2, 2, 1}. Requires 4 bins.

---

### 6. Graph Coloring

**Types of Graph Coloring Problems**
* Vertex coloring
* Edge coloring
* Face coloring

**Vertex Coloring**
* **Definition:** It is the assignment of colors to vertices in a graph such that no two adjacent vertices share the same color.
* **Properties:**
    * A graph is 0-colorable if and only if $V=\emptyset$.
    * A graph is 1-colorable if and only if $E=\emptyset$.
* **Chromatic Number Notation:** The chromatic number of a 2-colorable graph is denoted as $\chi(G)=2$.

## Module V: Algorithm Analysis and Design

### 1. Graph Coloring
Graph coloring is a fundamental concept in graph theory where colors (or symbols/numbers) are assigned to specific components of a graph subject to certain constraints.

**Key Terminology**
* **Chromatic Number ($\chi(G)$):** The minimum number of colors required to color a graph.
* **Null Graph:** A graph containing only vertices and no edges. Its chromatic number is $\chi(G) = 1$.
* **Standard Graphs:** For all other graphs containing edges, $\chi(G) \ge 2$.
* **k-colorable:** A graph is considered k-colorable if it can be colored using $k$ colors.
* **k-chromatic graph:** A graph whose exact chromatic number is $k$.
* **Color Class:** A subset of vertices that are all assigned the exact same color.
* **Four Color Theorem:** For every planar graph, the chromatic number is always less than or equal to 4.

**Types of Graph Coloring**
* **Vertex Coloring:** The most common form of graph coloring, focusing on coloring the vertices such that no adjacent vertices share a color.
* **Edge Coloring:** Given a graph $G=(V,E)$, this involves assigning a color to each edge so that no two adjacent edges share the same color.
* **Face Coloring (Map Coloring):** For a planar graph, this assigns a color to each face or region so that no two faces sharing a boundary have the same color.

---

### 2. Graph Coloring Approximation Algorithm
The graph coloring problem is famously an NP-Complete problem, meaning there is no known polynomial-time solution for it. However, we can use approximation algorithms to find a near-optimal solution.

Below is the Greedy Approximation Algorithm for Vertex Coloring:

```text
Algorithm Approximate_Graph_Coloring(G, n)
{
    for i = 1 to n do 
    {
        for c = 1 to n do 
        {
            If no vertex adjacent to vi has color c 
            {
                Color vi with c
                Break
            }
        }
    }
}
```

* **Time Complexity:** The time complexity for this approximation algorithm is $O(n^3)$.

**Applications of Graph Coloring**
Graph coloring has several highly practical real-world applications:
* Preparing timetables.
* Scheduling tasks or processes.
* Register allocation in compilers.
* Mobile radio frequency assignment.
* Map coloring.

---

### 3. Randomized Algorithms
While a Deterministic Algorithm produces an output and takes a running time that are purely functions of the input, a Randomized Algorithm uses random bits. An algorithm that uses random numbers anywhere in its logic to decide what to do next is classified as a Randomized Algorithm.

**Why use Randomized Algorithms?**
* They are typically used to reduce the time complexity or space complexity found in other standard algorithms.
* They hope to achieve good performance in the "average case" across all possible choices of random bits.
* For many computationally heavy tasks (like NP-Hard or NP-Complete problems), a randomized algorithm is often the simplest and fastest solvable approach.

**A Note on Random Number Generation**
* Computers cannot naturally generate truly random numbers; they generate pseudorandom numbers using a mathematical formula.
* Because these formulas are predictable, pseudorandom numbers are not secure enough for security applications.
* To generate truly random numbers, specialized devices measuring radioactive decay or lava lamps are required.

---

### 4. Types of Randomized Algorithms

**A. Las Vegas Algorithms**
* **Accuracy:** The output is always correct and optimal.
* **Time:** The running time is a random number and is not bounded.
* **Example 1 (Finding an 'a'):** In an array of $n$ elements (half 'a's, half 'b's), randomly choose elements until 'a' is found. It succeeds with a probability of 1. Expected iterations are 2, giving a time complexity of $O(1)$.
* **Example 2:** Randomized Quick Sort.

**B. Monte Carlo Algorithms**
* **Accuracy:** May produce a correct output only with some probability of success.
* **Time:** Runs for a strictly fixed number of steps, making the running time deterministic.
* **Example 1 (Finding the Median):** To find a number $\ge$ the median in a massive dataset (e.g., $n = 100,000,000,000$), randomly choose 100 numbers, find the maximum, and return it. Running time is $O(1)$, and the probability of failure is infinitesimally small ($\frac{1}{2^{100}}$).
* **Example 2 (Finding an 'a' with bounded iterations):** Similar to the Las Vegas example, but the algorithm halts after $k$ iterations whether 'a' is found or not. Running time is bounded to $O(k)$. The probability of success after $k$ iterations is $1 - (\frac{1}{2})^k$.

---

### 5. Case Study: Randomized Quick Sort

**Deterministic Quick Sort**
* Always picks a predefined pivot (like the 1st element) and partitions the array.
* **Worst Case Time Complexity:** $O(n^2)$ (occurs if the array is already sorted).
* **Average Expected Time Complexity:** $O(n \log n)$.

**Randomized Quick Sort (Las Vegas)**
* Instead of picking a rigid pivot, the algorithm searches for a Central Pivot.
* It uniformly picks a random element $x$.
* It counts elements smaller ($sc$) and greater ($gc$) than $x$.
* If both $sc \ge \frac{n}{4}$ and $gc \ge \frac{n}{4}$, then $x$ is declared a central pivot, and the array is partitioned.

**Analysis of Randomized Quick Sort:**
* Finding a central pivot requires an expected loop run time of $O(n)$.
* In the worst case, the partition divides the array such that one side has $\frac{n}{4}$ elements and the other has $\frac{3n}{4}$ elements.
* The worst-case height of the recursion tree is $\log_{\frac{4}{3}} n$, which simplifies to $O(\log n)$.
* **Overall Worst-Case Time Complexity:** Solved via the recurrence $T(n) < T(\frac{n}{4}) + T(\frac{3n}{4}) + O(n)$, the final time complexity strictly bounds to $O(n \log n)$.

You are absolutely right, and I apologize for missing those. I summarized the examples in the previous notes instead of providing the exact pseudocode that was detailed in the document.

Here are the complete algorithms exactly as they appear in your notes:

### 1. Las Vegas Algorithm: Finding an 'a'
This algorithm guarantees finding 'a' but its running time varies.

```text
Algorithm findingA_LV LV(A,n) 
{ 
    repeat 
    { 
        Randomly choose one element out of n elements 
    } until('a' is found) 
} 
```

### 2. Monte Carlo Algorithm: Finding an 'a'
This algorithm has a bounded running time (up to $k$ iterations) but might fail to find 'a' if it runs out of attempts.

```text
Algorithm findingA_MC MC(A,n,k) 
{ 
    i=0; 
    repeat 
    { 
        Randomly select one element out of n elements 
        i=i+1; 
    } until(i=k or 'a' is found); 
} 
```

### 3. Deterministic Quick Sort Algorithm
This is the standard quicksort approach where the pivot choice is fixed.

```text
Algorithm QuickSort(A[ ], low, high) 
1. If low >= high, then EXIT 
2. Let the 1st element of A as the pivot element, say x 
3. Partition A[low..high] into two subarrays. The first subarray has all the elements of A that are less than x and the second subarray has all those that are greater than x. Now the index of x be pos. 
4. QuickSort(A, low, pos-1) 
5. QuickSort(A, pos+1, high) 
```

### 4. Randomized Quick Sort Algorithm
This version uses randomness to find a "central pivot" to avoid the worst-case scenario.

```text
Algorithm randQuickSort(A[], low, high) 
1. If low >= high, then EXIT 
2. While pivot 'x' is not a Central Pivot. 
    2.1. Choose uniformly at random a element from A[low..high]. Let the randomly picked element be x. 
    2.2. Count elements in A[low..high] that are smaller than x. Let this count be sc. 
    2.3. Count elements in A[low..high] that are greater than x. Let this count be gc. 
    2.4. Let n = (high-low+1). If sc >= n/4 and gc >= n/4, then x is a central pivot. 
3. Partition A[low..high] into two subarrays. The first subarray has all the elements of A that are less than x and the second subarray has all those that are greater than x. Now the index of x be pos. 
4. randQuickSort(A, low, pos-1) 
5. randQuickSort(A, pos+1, high) 
```