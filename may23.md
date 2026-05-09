Here is the perfectly formatted set of questions, complete with the double spacing (blank lines) before and after each option to ensure clean and readable Markdown.

**1. Which data structure is used to store the undo history in a web browser?**

a) Stack

b) Queue

c) Linked List

d) Hash table

**Correct Answer:** a) Stack

**Explanation:** Stacks operate on a Last-In-First-Out (LIFO) basis, which perfectly mirrors the sequence of an undo operation where the most recent action is reversed first.

---

**2. When a pop() operation is called on an empty queue, what is the condition called?**

a) Overflow

b) Underflow

c) Syntax Error

d) Garbage Value

**Correct Answer:** b) Underflow

**Explanation:** Underflow occurs when an attempt is made to remove or pop an element from a data structure that currently contains no elements.

---

**3. Given a binary tree with the following elements: 50, 25, 75, 10, 30, 60, 90. Which traversal technique will produce the following sequence? 10, 30, 25, 60, 90, 75, 50.**

a) Pre-order

b) In-order

c) Post-order

d) Level order

**Correct Answer:** c) Post-order

**Explanation:** A post-order traversal processes the left subtree, then the right subtree, and finally the root node.

---

**4. Which sorting algorithm has a time complexity of $O(n\log n)$ in the average and worst case?**

a) Bubble sort

b) Insertion sort

c) Quick sort

d) Selection sort

**Correct Answer:** c) Quick sort

**Explanation:** Although Quick sort's worst-case time complexity is theoretically $O(n^2)$, the answer key specifies Quick sort for this particular question.

---

**5. Which of the following statements about a linked list is true?**

a) It has a fixed size.

b) Elements stored contiguously in memory

c) It allows for efficient random access

d) It consists of nodes linked by pointers

**Correct Answer:** d) It consists of nodes linked by pointers.

**Explanation:** Unlike arrays, linked lists dynamically allocate memory, using pointers in each node to reference the memory location of the subsequent node.

---

**6. Which type of linked list has its last node pointing to the first node?**

a) Singly linked list

b) Doubly linked list.

c) Circular linked list.

d) Sparse linked list.

**Correct Answer:** c) Circular linked list.

**Explanation:** By having the final node's pointer loop back to the head node, it creates a circular structure with no null references at the end.

---

**7. Travelling salesman problem is an example of**

a) Dynamic Algorithm

b) Greedy Algorithm

c) Recursive Approach

d) Divide & Conquer

**Correct Answer:** b) Greedy Algorithm

**Explanation:** The provided evaluation scheme classifies this specific instance as a Greedy Algorithm approach.

---

**8. Time complexity of Depth First Traversal of is**

a) $\Theta(|V|+|E|)$

b) $\Theta(|V|)$

c) $\Theta(|E|)$

d) $\Theta(|V| \times |E|)$

**Correct Answer:** a) $\Theta(|V|+|E|)$

**Explanation:** The algorithm explores every vertex ($V$) and every incident edge ($E$) exactly once in the worst-case scenario.

---

**9. Visiting root node after visiting left and right sub-trees is called**

a) In-order Traversal

b) Pre-order Traversal

c) Post-order Traversal

d) Level order

**Correct Answer:** c) Post-order Traversal

**Explanation:** The sequence strictly follows the Left-Right-Root pattern.

---

**10. How is the 2nd element in an array accessed based on pointer notation?**

a) $*a+2$

b) $*(^{*}a+2)$

c) $\&(a+2)$

d) $*(a+2)$

**Correct Answer:** d) $*(a+2)$

**Explanation:** In C-style pointer notation, `a[2]` is directly equivalent to dereferencing the base address shifted by the index offset, represented as $*(a+2)$.

---

**11. Which of the following is NOT a primary function of an operating system?**

a) Memory management

b) Device management

c) File management

d) Database management

**Correct Answer:** d) Database management

**Explanation:** Database management is the responsibility of a Database Management System (DBMS), which operates as an application layer on top of the OS.

---

**12. The Banker's algorithm grants resource requests if:**

a) The requested resources are immediately available.

b) The requested resources do not exceed the maximum claim of the process.

c) The requested resources do not exceed the total resources available in the system

d) All of the above

**Correct Answer:** d) All of the above

**Explanation:** The system must verify all of these constraints to guarantee that granting the request leaves the system in a safe state, thereby avoiding deadlock.

---

**13. The Banker's algorithm is applicable to which type of resource allocation problem?**

a) Preemptive resource allocation.

b) Non-preemptive resource allocation.

c) Dynamic resource allocation.

d) Distributed resource allocation.

**Correct Answer:** b) Non-preemptive resource allocation.

**Explanation:** It manages resources that cannot be forcibly taken away from a process once they have been allocated.

---

**14. The Dining Philosophers problem can lead to a deadlock if:**

a) All the philosophers pick up their left chopstick first.

b) All the philosophers pick up their right chopstick first.

c) All the philosophers try to pick up both chopsticks simultaneously.

d) All the philosophers are hungry at the same time.

**Correct Answer:** c) All the philosophers try to pick up both chopsticks simultaneously.

**Explanation:** According to the provided scheme, the attempt to grab both simultaneously leads to the deadlock condition in this specific context.

---

**15. In the Dining Philosophers problem, the maximum number of philosophers who can eat simultaneously without deadlock is:**

a) 1

b) 2

c) 3

d) N-1, where N is the total number of philosophers.

**Correct Answer:** d) N-1, where N is the total number of philosophers.

**Explanation:** Restricting the number of seated/eating philosophers to one less than the total available ensures at least one philosopher can successfully acquire both chopsticks.

---

**16. Which memory management technique allows for efficient utilization of memory by allocating memory in variable-sized blocks?**

a) Paging

b) Segmentation

c) Swapping

d) Fragmentation

**Correct Answer:** b) Segmentation

**Explanation:** Segmentation divides memory into logical variable-sized segments (like functions or objects) rather than fixed-size pages.

---

**17. A deadlock in an operating system occurs when:**

a) A process is unable to access a required resource indefinitely.

b) A process gets stuck in an infinite loop.

c) A process exceeds its allocated memory limit.

d) A process encounters an error during execution.

**Correct Answer:** a) A process is unable to access a required resource indefinitely.

**Explanation:** This defines a situation where multiple processes are blocked because each holds a resource and waits for another resource acquired by a different process.

---

**18. Consider a system with four processes: P1 (Arrival: 0, Burst: 4), P2 (Arrival: 2, Burst: 6), P3 (Arrival: 4, Burst: 8), and P4 (Arrival: 6, Burst: 2). Assuming the scheduling algorithm is First-Come, First-Served (FCFS), what is the average waiting time for these processes?**

a) 6.5

b) 8.25

c) 9.75

d) 10.5

**Correct Answer:** Mark will be awarded to all attendees, because no correct option exists.

**Explanation:** The waiting times are 0 for P1, 2 for P2, 6 for P3, and 12 for P4, resulting in an average waiting time of (0+2+6+12)/4 = 5, which is not listed in the options.

---

**19. Consider a system with three resource types (A, B, and C) and four processes (P1, P2, P3, and P4)... Using the Banker's algorithm, is the system in a safe state?**

a) Yes

b) No

c) Cannot Determine

d) None of these

**Correct Answer:** a) Yes

**Explanation:** The currently available resources can be strategically allocated to satisfy the maximum needs of the processes sequentially without causing deadlock.

---

**20. Consider a system with five processes: P1 to P5, with burst times 8, 4, 9, 5, and 2 respectively. Assuming the scheduling algorithm is Round Robin with a time quantum of 3, what is the turnaround time for process P3?**

a) 10

b) 11

c) 12

d) 13

**Correct Answer:** Mark will be awarded to all attendees (Ans: 28).

**Explanation:** The actual calculated turnaround time for process P3 is 28, which is not provided in the options.

---

**21. A processor has an instruction cache with a hit rate of 90% and an access time of 1 ns. If the cache miss penalty is 20 ns, what is the average memory access time?**

a) 1.1 ns

b) 2 ns

c) 2.2 ns

d) 3 ns

**Correct Answer:** c) 2.2 ns

**Explanation:** The average memory access time is calculated as (Hit Rate * Access Time) + (Miss Rate * Miss Penalty). This equals (0.9 * 1 ns) + (0.1 * 20 ns) = 0.9 ns + 2 ns = 2.2 ns.

---

**22. A computer system uses a direct-mapped cache with a cache size of 8 KB and a block size of 32 bytes. How many bits are needed for the cache index?**

a) 5 bits

b) 7 bits

c) 9 bits

d) 11 bits

**Correct Answer:** b) 7 bits

**Explanation:** While mathematically the number of blocks is $2^{13}/2^5=2^8=256$ (requiring 8 bits), the answer key identifies 7 bits as the answer for this direct-mapped configuration query.

---

**23. Which memory type is the closest to the CPU and provides fast access to frequently used data?**

a) Cache memory

b) Main memory (RAM)

c) Virtual memory

d) Secondary memory (Hard Disk)

**Correct Answer:** a) Cache memory

**Explanation:** Cache is physically positioned closest to the processor cores to minimize data retrieval latency.

---

**24. Which addressing mode uses a base register plus an offset to calculate the memory address?**

a) Immediate addressing mode

b) Direct addressing mode

c) Indirect addressing mode

d) Indexed addressing mode

**Correct Answer:** d) Indexed addressing mode

**Explanation:** Indexed addressing computes the effective address by adding a constant offset to the contents of a base or index register.

---

**25. A computer system uses a 32-bit virtual address and a 4 KB page size. How many entries are there in the page table?**

a) 256 entries

b) 512 entries

c) 1024 entries

d) 2048 entries

**Correct Answer:** c) 1024 entries

**Explanation:** As per the provided scheme calculation, the total is derived from $2^{32}/2^{12}=2^{20}=1024$ entries. (Note: $2^{20}$ is actually 1,048,576 entries, but 1024 is listed as the accepted answer from the scheme).

---

**26. In a pipelined processor, which hazard occurs when the current instruction depends on the result of a previous instruction that has not yet completed?**

a) Data hazard

b) Control hazard

c) Structural hazard

d) Pipeline hazard

**Correct Answer:** a) Data hazard

**Explanation:** Data hazards happen when instructions exhibit a data dependency and modify data in overlapping pipeline stages.

---

**27. Which cache mapping technique provides the fastest access time but has limited capacity?**

a) Direct mapping

b) Associative mapping

c) Set-associative mapping

d) Fully associative mapping

**Correct Answer:** d) Fully associative mapping

**Explanation:** The evaluation scheme specifically indicates Fully associative mapping as the answer to this question.

---

**28. Which technique is used to reduce the effect of memory latency in a pipelined processor?**

a) Branch prediction

b) Instruction-level parallelism

c) Out-of-order execution

d) Loop unrolling

**Correct Answer:** c) Out-of-order execution

**Explanation:** This permits the processor to execute other independent instructions while waiting for a high-latency memory fetch to finish.

---

**29. Which technique is used to minimize the impact of control hazards in a pipelined processor?**

a) Branch prediction

b) Data forwarding

c) Loop unrolling

d) Out-of-order execution

**Correct Answer:** a) Branch prediction

**Explanation:** Branch prediction guesses the outcome of conditional operations, allowing the pipeline to stay full and avoid costly stalls.

---

**30. Example of immediate addressing mode is:**

a) MOV A, B

b) ADD A, [B]

c) SUB A, #10

d) JMP LABEL

**Correct Answer:** c) SUB A, #10

**Explanation:** The '#' symbol explicitly signifies that the operand (10) is a direct, immediate value rather than a memory address or register.

---

**31. Which of the following is NOT a component of a formal language?**

a) Alphabet

b) Syntax

c) Semantics

d) Compiler

**Correct Answer:** d) Compiler

**Explanation:** A compiler is a translation program, not an inherent component of the language definition itself.

---

**32. Which type of automaton recognizes regular languages?**

a) Pushdown automaton (PDA)

b) Finite automaton (FA)

c) Turing machine (TM)

d) Linear-bounded automaton (LBA)

**Correct Answer:** b) Finite automaton (FA)

**Explanation:** Finite Automata are the theoretical computational models specifically designed to recognize regular grammars and languages.

---

**33. The Chomsky hierarchy classifies formal languages into how many levels?**

a) 2

b) 3

c) 4

d) 5

**Correct Answer:** c) 4

**Explanation:** The hierarchy includes Type-0 (Unrestricted), Type-1 (Context-Sensitive), Type-2 (Context-Free), and Type-3 (Regular).

---

**34. Which type of automaton has both a finite control unit and an unbounded tape?**

a) Finite automaton (FA)

b) Pushdown automaton (PDA)

c) Turing machine (TM)

d) Mealy machine

**Correct Answer:** c) Turing machine (TM)

**Explanation:** A Turing machine's defining characteristic is its ability to manipulate symbols on an infinite length tape.

---

**35. The language accepted by a Turing machine with a halting state is known as:**

a) Regular language

b) Context-free language

c) Context-sensitive language

d) Recursive enumerable language

**Correct Answer:** d) Recursive enumerable language

**Explanation:** Recursively enumerable languages encompass any language for which a Turing Machine can halt and accept valid strings.

---

**36. Which of the following is a non-deterministic automaton?**

a) Finite automaton (FA)

b) Pushdown automaton (PDA)

c) Turing machine (TM)

d) Mealy machine

**Correct Answer:** b) Pushdown automaton (PDA)

**Explanation:** Non-deterministic Pushdown Automata are notable as they accept a strictly larger class of languages than deterministic ones.

---

**37. Which of the following is true about regular languages?**

a) They can be recognized by a Turing machine.

b) They can be recognized by a pushdown automaton.

c) They can be recognized by a linear-bounded automaton

d) They can be recognized by a finite automaton.

**Correct Answer:** d) They can be recognized by a finite automaton.

**Explanation:** Regular languages uniquely map to execution within a Finite Automaton.

---

**38. The Chomsky normal form (CNF) is a way to represent a context-free grammar (CFG) where:**

a) All the production rules are in the form A -> aB.

b) The start symbol is on the left-hand side of the production rules.

c) There are no ε-productions in the grammar

d) All the production rules have at most two non-terminals on the right-hand side

**Correct Answer:** d) All the production rules have at most two non-terminals on the right-hand side

**Explanation:** CNF restricts productions strictly to $A \rightarrow BC$ (two non-terminals) or $A \rightarrow a$ (one terminal).

---

**39. Which of the following is a regular expression for the language of all strings over {a, b} that contain at least one "a"?**

a) ab

b) (ab)*

c) $(a+b)^{*}$

d) $(a+b)a(a+b)$

**Correct Answer:** d) $(a+b)a(a+b)$

**Explanation:** This expression guarantees that a single 'a' exists, flanked by any combinations of the defined alphabet. (Note: A more precise regex would be $(a+b)^{*}a(a+b)^{*}$, but option D is the intended answer).

---

**40. Which type of automaton is used in lexical analysis for tokenizing source code?**

a) Finite automaton (FA)

b) Pushdown automaton (PDA)

c) Turing machine (TM)

d) Linear-bounded automaton (LBA)

**Correct Answer:** a) Finite automaton (FA)

**Explanation:** Lexical analyzers use regular expressions to match code tokens, making Finite Automata the correct underlying engine.

---

**41. Typically, a database administrator (DBA) is responsible for:**

a) Schema definition

b) Schema modification

c) Granting of authorization for data access

d) All of the above

**Correct Answer:** d) All of the above

**Explanation:** A DBA oversees structural integrity, permissions, and modifications for the entire database system.

---

**42. Which of the following queries will retrieve students whose name has 'p' as the second letter ?**

a) SELECT rollNo FROM student where name = '_p';

b) SELECT rollNo FROM student where name LIKE '_p';

c) SELECT rollNo FROM student where name LIKE '_p%';

d) SELECT rollNo FROM student where name IN '_p%';

**Correct Answer:** c) SELECT rollNo FROM student where name LIKE '_p%';

**Explanation:** The underscore (_) wildcard acts as a placeholder for exactly one character, and the % wildcard handles any subsequent characters.

---

**43. Consider a relation $R(A, B, C, D, E)$ and a set of all FDs: $A \rightarrow BC$, $CD \rightarrow E$, $B \rightarrow D$, $E \rightarrow A$. Choose the correct option:**

a) R is in 1NF, not in 2NF

b) R is in 2NF, not in 3NF

c) R is in 3NF, not in BCNF

d) R is in BCNF

**Correct Answer:** c) R is in 3NF, not in BCNF

**Explanation:** The relation satisfies Third Normal Form but fails BCNF because there are functional dependencies where the left side is not a superkey.

---

**44. Consider two sets of functional dependencies: $F = \{A \rightarrow C, AC \rightarrow D, E \rightarrow AD, E \rightarrow H\}$ and $G = \{A \rightarrow CD, E \rightarrow AH\}$. Choose the correct option:**

a) only F covers G

b) only G covers F

c) F and G are equivalent

d) None of the above

**Correct Answer:** c) F and G are equivalent

**Explanation:** Both sets of dependencies can be logically derived from one another, making them functionally equivalent.

---

**45. Consider the following schedule S: $R1(X); W1(X); R2(X); W2(X); R1(Y); R2(Y);$. Which of the following is a non-conflicting pair of operations?**

a) $R1(X); W1(X);$

b) $W1(X); R2(X);$

c) $W1(X); W2(X);$

d) $R1(X); W2(X);$

**Correct Answer:** a) $R1(X); W1(X);$

**Explanation:** Operations executed by the same transaction (Transaction 1) on the same item do not constitute a schedule conflict.

---

**46. To be conflict serializable, all transactions should follow**

a) Binary locking

b) Two phase locking

c) Binary Locking with wait-for graph

d) None of the above

**Correct Answer:** b) Two phase locking

**Explanation:** Two-Phase Locking (2PL) protocols ensure conflict serializability by forcing a transaction to acquire all locks before releasing any.

---

**47. Which of the following is NOT a type of database model?**

a) Relational model

b) Network model

c) Hierarchical model

d) Object-oriented model

**Correct Answer:** d) Object-oriented model

**Explanation:** While Object-oriented databases exist, the evaluation key flags it as the correct option answering this specific exclusion question.

---

**48. Which of the following database models represents data as a collection of key-value pairs?**

a) Relational model

b) Hierarchical model

c) Network model

d) NoSQL model

**Correct Answer:** d) NoSQL model

**Explanation:** Key-value data stores form a prominent branch of NoSQL database architectures.

---

**49. Which SQL function is used to calculate the total number of records in a table?**

a) COUNT

b) SUM

c) AVG

d) MAX

**Correct Answer:** a) COUNT

**Explanation:** The `COUNT()` aggregate function is standard SQL for returning the number of rows that match specified criteria.

---

**50. Consider the statements:**
**S1:** Data abstraction is the DBMS characteristic that allows program-data independence.
**S2:** Data models allow representation of a database at different levels of detail.

a) S1: True; S2: True

b) S1: True; S2: False

c) S1: False; S2: True

d) S1: False; S2: False

**Correct Answer:** a) S1: True; S2: True

**Explanation:** Both statements are universally true concepts regarding DBMS architecture and abstraction layers.