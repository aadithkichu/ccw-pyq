Here is the neatly formatted set of questions with double spacing (a blank line) before and after every option to ensure it renders perfectly with clear spacing in Markdown.

## **Operating Systems**

**1. In a timesharing operating system, when the time slot assigned to a process is completed, the process switches from the current state to?**

a) Suspended state

b) Terminated state

c) Ready state

d) Blocked state

**Correct Answer:** c) Ready state

**Explanation:** When a time quantum expires in round-robin or timesharing scheduling, the OS preempts the running process and places it back into the ready queue to wait for its next CPU turn.

---

**2. Dirty bit is used to indicate which of the following?**

a) A page fault has occurred

b) A page has corrupted data

c) A page has been modified after being loaded into cache

d) An illegal access of page

**Correct Answer:** c) A page has been modified after being loaded into cache

**Explanation:** The dirty bit tracks whether a memory block or page has been modified (written to) by the CPU. If set, the page must be written back to the disk before it can be replaced.

---

**3. What is a short-term scheduler?**

a) It selects which process has to be brought into the ready queue

b) It selects which process has to be executed next and allocates CPU

c) It selects which process to remove from memory by swapping

d) None of the mentioned

**Correct Answer:** b) It selects which process has to be executed next and allocates CPU

**Explanation:** The short-term scheduler (or CPU scheduler) frequently selects an available process from the ready queue to assign to the CPU for execution.

---

**4. If a process fails, most operating systems write the error information to a:**

a) new file

b) another running process

c) log file

d) none of the mentioned

**Correct Answer:** c) log file

**Explanation:** Operating systems typically maintain log files to record system events, errors, and crash details for diagnostic and debugging purposes.

---

**5. If a process is executing in its critical section, then no other processes can be executing in their critical section. What is this condition called?**

a) mutual exclusion

b) critical exclusion

c) synchronous exclusion

d) asynchronous exclusion

**Correct Answer:** a) mutual exclusion

**Explanation:** Mutual exclusion is a core concurrency control property ensuring that only one process or thread can access a shared resource (critical section) at any given time.

---

**6. When are the register context and stack of thread deallocated?**

a) when the thread terminates

b) when the thread blocks

c) when the thread unblocks

d) when the thread spawns

**Correct Answer:** a) when the thread terminates

**Explanation:** A thread's stack and register states are unique local resources; the OS reclaims this memory only when the thread has completely finished execution.

---

**7. Out of these page replacement algorithms, which one suffers from Belady's anomaly?**

a) LRU

b) FIFO

c) Both LRU and FIFO

d) Optimal Page Replacement

**Correct Answer:** b) FIFO

**Explanation:** Belady's anomaly is a phenomenon specifically observed in the First-In-First-Out (FIFO) algorithm, where increasing the number of page frames actually increases the number of page faults.

---

**8. Which one of these is NOT shared by the same process's threads?**

a) Address Space

b) Stack

c) Message Queue

d) File Descriptor Table

**Correct Answer:** b) Stack

**Explanation:** While threads within the same process share code, data, and OS resources (like file descriptors), each thread requires its own independent stack to manage local variables and function calls.

---

**9. Which of these disk scheduling policies results in minimum head movement?**

a) Circular scan

b) Elevator

c) FCS

d) None of the above

**Correct Answer:** d) None of the above

**Explanation:** Algorithms like Shortest Seek Time First (SSTF) generally provide the minimum head movement, but this option is not listed among the choices.

---

**10. In a computer system that consists of $n$ number of CPUs, the maximum processes that can exist in the Ready State would be:**

a) Independent of $n$

b) $2n$

c) $n^2$

d) $n$

**Correct Answer:** a) Independent of $n$

**Explanation:** The number of CPUs limits how many processes can be in the Running state concurrently. The Ready state queue size is dictated by main memory and system limits, totally independent of CPU count.

---

## **Database Management Systems (DBMS)**

**11. Which of the following is preserved in execution of transaction in isolation?**

a) Atomicity

b) Isolation

c) Durability

d) Consistency

**Correct Answer:** d) Consistency

**Explanation:** The isolation property guarantees that concurrent execution of transactions leaves the database in the same consistent state as if they were executed serially.

---

**12. Given the following relation instance:**
x | y | z
1 | 4 | 2
1 | 5 | 3
1 | 6 | 3
3 | 2 | 2

a) $XY \rightarrow Z$ and $Z \rightarrow Y$

b) $YZ \rightarrow X$ and $Y \rightarrow Z$

c) $YZ \rightarrow X$ and $X \rightarrow Z$

d) $XZ \rightarrow Y$ and $Y \rightarrow X$

**Correct Answer:** b) $YZ \rightarrow X$ and $Y \rightarrow Z$

**Explanation:** Every unique combination of $(Y,Z)$ in the table determines a single $X$, and every unique $Y$ value strictly determines a single $Z$.

---

**13. Identify the statement among the following that is FALSE.**

a) The relation in which all keys have only a single attribute is in its 2NF

b) A relation that has two attributes is in its BCNF

c) The prime attribute can depend transitively on any key in the case of a relation that is in its BCNF

d) The prime attribute can depend transitively on any key in the case of a relation that is in its 3NF

**Correct Answer:** c) The prime attribute can depend transitively on any key in the case of a relation that is in its BCNF

**Explanation:** In Boyce-Codd Normal Form (BCNF), there are strictly no dependencies (transitive or partial) on anything other than a superkey. Statement C is theoretically false.

---

**14. Which one of the following queries always gives the same answer as the nested query shown below:**
`select * from R where a in (select S.a from S)`

a) `select R.* from R, S where R.a = S.a`

b) `select distinct R.* from R, S where R.a = S.a`

c) `select R.* from R, (select distinct a from S) as S1 where R.a = S1.a`

d) `select R.* from R, S where R.a = S.a and is unique R`

**Correct Answer:** c) `select R.* from R, (select distinct a from S) as S1 where R.a = S1.a`

**Explanation:** The IN subquery acts as an existence check, avoiding duplication of rows from $R$. Option C replicates this by explicitly ensuring the join is made against a DISTINCT set of $S.a$ values.

---

**15. The term for information that describes what type of data is available in a database is:**

a) Data dictionary

b) Data repository

c) Index data

d) Metadata

**Correct Answer:** a) Data dictionary

**Explanation:** A data dictionary stores the metadata, which is the "data about data" defining the structure, constraints, and schemas of the database.

---

**16. Consider the relation Cinema(theater, address, capacity). Which of the following options will be needed at the end of the SQL query `SELECT P1.address FROM Cinema P1` such that it always finds the addresses of theaters with maximum capacity?**

a) `WHERE P1.capacity >= All (select P2.capacity from Cinema P2)`

b) `WHERE P1.capacity >= Any (select P2.capacity from Cinema P2)`

c) `WHERE P1.capacity > All (select max(P2.capacity) from Cinema P2)`

d) `WHERE P1.capacity > Any (select max(P2.capacity) from Cinema P2)`

**Correct Answer:** a) `WHERE P1.capacity >= All (select P2.capacity from Cinema P2)`

**Explanation:** Using `>= ALL` ensures the selected theater's capacity is greater than or equal to every single capacity present in the entire table, effectively locating the maximum.

---

**17. Consider the following two statements about database transaction schedules:**
**I.** Strict two-phase locking protocol generates conflict serializable schedules that are also recoverable.
**II.** Timestamp-ordering concurrency control protocol with Thomas Write Rule can generate view serializable schedules that are not conflict serializable.
**Which of the above statements is/are TRUE?**

a) Both I and II

b) I only

c) II only

d) Neither I nor II

**Correct Answer:** a) Both I and II

**Explanation:** Strict 2PL prevents cascading rollbacks (making it recoverable) while maintaining serializability. Thomas Write Rule purposefully ignores obsolete writes, breaking conflict serializability but retaining view serializability.

---

**18. B+ Trees are considered BALANCED because:**

a) The lengths of the paths from the root to all leaf nodes are all equal.

b) The lengths of the paths from the root to all leaf nodes differ from each other by at most 1.

c) The number of children of any two non-leaf sibling nodes differ by at most 1.

d) The number of records in any two leaf nodes differ by at most 1.

**Correct Answer:** a) The lengths of the paths from the root to all leaf nodes are all equal.

**Explanation:** A defining structural property of a B+ tree is that every leaf node resides at the exact same depth from the root.

---

**19. Which of the following relational query languages have the same expressive power?**
**I)** Relational algebra
**II)** Tuple relational calculus restricted to safe expressions
**III)** Domain relational calculus restricted to safe expressions.

a) II and III only

b) I and II only

c) I and III only

d) I, II and III

**Correct Answer:** d) I, II and III

**Explanation:** Known as Codd's Theorem, it dictates that Relational Algebra and both safe forms of Relational Calculus possess identical expressive capabilities.

---

**20. An entity in A is associated with at most one entity in B. An entity in B, however, can be associated with any number (zero or more) of entities in A.**

a) One-to-many

b) One-to-one

c) Many-to-many

d) Many-to-one

**Correct Answer:** d) Many-to-one

**Explanation:** From the perspective of A to B, multiple entities from A map to a single entity in B, forming a Many-to-One relationship.

---

## **Data Structures & Algorithms**

**21. Convert the following infix expression into its equivalent postfix expression: $(A+B\wedge D)/(E-F)+G$**

a) $(A~B~D\wedge+E~F-/G+)$

b) $(A~B~D+\wedge E~F-/G+)$

c) $(A~B~D\wedge+E~F/-G+)$

d) $(A~B~D~E~F+\wedge/-G+)$

**Correct Answer:** a) $(A~B~D\wedge+E~F-/G+)$

**Explanation:** Resolving through standard operator precedence (exponentiation $\wedge$, then division $/$, then addition/subtraction), operators are systematically pushed to the right of their operands.

---

**22. The result of preorder traversal is same as:**

a) Depth-first order

b) Breadth-first search

c) Topological order

d) Linear order

**Correct Answer:** a) Depth-first order

**Explanation:** Preorder traversal deeply explores down a single branch before backtracking, mechanically mirroring a Depth-First Search (DFS).

---

**23. Queues serve major role in:**

a) Simulation of recursion

b) Simulation of arbitrary linked list

c) Simulation of limited resource allocation

d) Simulation of heap sort

**Correct Answer:** c) Simulation of limited resource allocation

**Explanation:** Queues are First-In-First-Out (FIFO) constructs, making them perfectly suited for scheduling models like CPU time, printer buffering, or allocating limited resources fairly.

---

**24. In the worst case, the number of comparisons needed to search a singly linked list of length $n$ for a given element is?**

a) $\log_2n$

b) $n/2$

c) $\log_2n-1$

d) $n$

**Correct Answer:** d) $n$

**Explanation:** In the absolute worst case (if the element is at the end or completely missing), one must linearly traverse and compare every single node in the list.

---

**25. If several elements are competing for the same bucket in the hash table, what is it called?**

a) Diffusion

b) Replication

c) Collision

d) Duplication

**Correct Answer:** c) Collision

**Explanation:** A collision happens when the hash function dictates that two distinct keys must map to the exact same index or bucket in the table.

---

**26. What is the number of edges present in a complete graph having $n$ vertices?**

a) $(n \times (n+1))/2$

b) $(n \times (n-1))/2$

c) $n$

d) Information given is insufficient

**Correct Answer:** b) $(n \times (n-1))/2$

**Explanation:** Every vertex connects to every other $n-1$ vertices exactly once. This is the combination formula $C(n, 2)$.

---

**27. Which of the following is not an in-place sorting algorithm?**

a) Selection sort

b) Heap sort

c) Quick sort

d) Merge sort

**Correct Answer:** d) Merge sort

**Explanation:** Standard Merge Sort is not in-place because it requires a secondary auxiliary array of size $O(n)$ to merge the sorted sub-arrays.

---

**28. The time complexity of heap sort in worst case is:**

a) $O(\log n)$

b) $O(n)$

c) $O(n \log n)$

d) $O(n^2)$

**Correct Answer:** c) $O(n \log n)$

**Explanation:** Building the initial heap takes $O(n)$, and extracting the max element $n$ times takes $O(\log n)$ per extraction, ensuring a strict worst-case bound of $O(n \log n)$.

---

**29. Suppose we are sorting an array of eight integers using quicksort, and we have just finished the first partitioning with the array looking like this: 2 5 1 7 9 12 11 10. Which statement is correct?**

a) The pivot could be either the 7 or the 9

b) The pivot could be the 7, but it is not the 9

c) The pivot is not the 7, but it could be the 9

d) Neither the 7 nor the 9 is the pivot

**Correct Answer:** a) The pivot could be either the 7 or the 9

**Explanation:** For a number to be a valid pivot, all numbers to its left must be smaller, and all to its right must be larger. Both 7 and 9 independently satisfy this rule in the given array.

---

**30. Consider a situation where swap operation is very costly. Which of the following sorting algorithms should be preferred so that the number of swap operations are minimized in general?**

a) Heap Sort

b) Selection Sort

c) Insertion Sort

d) Merge Sort

**Correct Answer:** b) Selection Sort

**Explanation:** Selection Sort minimizes memory writes by capping the total number of element swaps to a maximum of $O(n)$ (one per traversal pass).

---

## **Computer Organization & Architecture**

**31. Match the following:**
(a) Immediate address mode $\rightarrow$ (1) Local variables
(b) Direct address mode $\rightarrow$ (2) Relocatable programs
(c) Indirect address mode $\rightarrow$ (3) Pointer
(d) Index addressing mode $\rightarrow$ (4) Locality of reference
(e) Base address mode $\rightarrow$ (5) Arrays
(f) Relative address mode $\rightarrow$ (6) Constant Operands

a) a6 b1 c3 d5 e2 f4

b) a5 b4 c6 d3 e1 f2

c) a3 b5 c2 d4 e1 f2

d) a6 b5 c2 d3 e1 f4

**Correct Answer:** a) a6 b1 c3 d5 e2 f4

**Explanation:** Standard architectural matching: Immediates load Constants (6); Pointers rely on Indirect mode (3); Array traversal uses Index mode (5); and Relative addressing capitalizes on Locality (4).

---

**32. Search concept used in associative memory is:**

a) Parallel search

b) Sequential Search

c) Binary Search

d) Selection search

**Correct Answer:** a) Parallel search

**Explanation:** Associative memory (Content-Addressable Memory) is uniquely designed to compare input search data against all stored memory blocks concurrently in parallel hardware.

---

**33. Memory interleaving is done to:**

a) Increase the amount of logical memory

b) Reduce memory access time

c) Simplify memory interfacing

d) Reduce page faults

**Correct Answer:** b) Reduce memory access time

**Explanation:** Interleaving splits physical memory into independent banks that can be accessed simultaneously, hiding memory access latency and significantly boosting throughput.

---

**34. Which of the following DMA transfer modes and interrupt handling mechanisms will enable the highest I/O bandwidth?**

a) Transparent DMA and Polling

b) Cycle-Stealing and Polling interrupts

c) Block Transfer and vectored interrupts

d) Block transfer and Vectored interrupts

**Correct Answer:** c) Block Transfer and vectored interrupts

**Explanation:** Block transfers allow large data bursts while mitigating bus arbitration overhead. Vectored interrupts route the CPU to the exact handler instantly, bypassing slow polling routines.

---

**35. Consider the following sequence of micro-operations:**
MBR <- PC
MAR <- X
PC <- Y
Memory <- MBR
**Which one of the following is a possible operation performed by this sequence?**

a) Instruction fetch

b) Operand fetch

c) Conditional branch

d) Initiation of interrupt service

**Correct Answer:** d) Initiation of interrupt service

**Explanation:** The program counter (PC) representing the return address is copied to MBR and pushed into memory at address X, while the PC branches to an interrupt routine at Y.

---

**36. Register renaming is done in pipelined processors:**

a) as an alternative to register allocation at compile time

b) for efficient access to function parameters and local variables

c) to handle certain kinds of hazards

d) as part of address translation

**Correct Answer:** c) to handle certain kinds of hazards

**Explanation:** Register renaming allows the hardware to dynamically allocate hidden physical registers, specifically resolving false data hazards like Write-After-Write (WAW) and Write-After-Read (WAR).

> **Note:** Question 37 was identical to Question 34 in the original source material.

---

**38. A cache has a 64 KB capacity, 128-byte lines (blocks), and is 4-way set associative. The system containing the cache uses 32-bit addresses. How many lines (blocks) and sets does the cache have?**

a) 64

b) 128

c) 256

d) 32

**Correct Answer:** b) 128

**Explanation:** Total lines = 64 KB / 128 bytes = 512 lines. Because it is 4-way associative, multiple lines share an index: 512 / 4 = 128 sets.

---

**39. A machine with $N$ different opcodes can contain how many different sequences of micro-operations.**

a) $2^N$

b) $N^N$

c) $N^2$

d) $N$

**Correct Answer:** d) $N$

**Explanation:** A distinct opcode simply acts as an execution trigger for its own unique sequence of low-level micro-operations (its microprogram). Thus, $N$ opcodes yield $N$ distinct sequences.

---

**40. How many 32K x 1 RAM chips are needed to provide a memory capacity of 256K-bytes?**

a) 8

b) 32

c) 64

d) 128

**Correct Answer:** c) 64

**Explanation:** Total required capacity is 256K * 8 bits. Each chip holds 32K * 1 bits. Dividing total required by chip capacity gives (256 * 8) / 32 = 64 chips.

---

## **Theory of Computation**

![alt text](image-2.png)

**Correct Answer:** a) ababaabaa

**Explanation:** Following the transitions for "ababaabaa", the automaton ends up back in the initial state when reading the fourth character 'b', which immediately forces it into the non-accepting dumping state.

---

**42. Can a DFA recognize a palindrome number?**

a) Yes

b) No

c) Yes, with input alphabet as $\Sigma^*$

d) Can't be determined

**Correct Answer:** b) No

**Explanation:** A Deterministic Finite Automaton possesses no external memory stack and fundamentally cannot count or remember strings of arbitrary length to reverse and compare them.

---

**43. Which of the following options is correct?**
**Statement 1:** Initial State of NFA is Initial State of DFA.
**Statement 2:** The final state of DFA will be every combination of final state of NFA.

a) Statement 1 is true and Statement 2 is true

b) Statement 1 is true and Statement 2 is false

c) Statement 1 can be true and Statement 2 is true

d) Statement 1 is false and Statement 2 is also false

**Correct Answer:** b) Statement 1 is true and Statement 2 is false

**Explanation:** In Subset Construction, the DFA's start state encapsulates the NFA's start state. However, a DFA state is marked final if it contains any NFA final state, not every combination.

---

**44. Which of the following statement is correct?**

a) All Regular grammar are context free but not vice versa

b) All context free grammar are regular but not vice versa

c) Regular grammar and context free grammar are the same entity

d) None of the mentioned

**Correct Answer:** a) All Regular grammar are context free but not vice versa

**Explanation:** Under the Chomsky hierarchy, the set of regular languages (Type 3) is entirely contained as a strict, smaller subset within context-free languages (Type 2).

---

**45. Suppose $A \rightarrow xBz$ and $B \rightarrow y$ then the simplified grammar would be:**

a) $A \rightarrow xyz$

b) $A \rightarrow xBz | xyz$

c) $A \rightarrow xBz | B | y$

d) none of the mentioned

**Correct Answer:** a) $A \rightarrow xyz$

**Explanation:** Because non-terminal B yields nothing but the terminal 'y', we can fully substitute 'y' anywhere B appears to safely eliminate the variable B.

---

**46. Given grammar G: (1) $S \rightarrow AS$ (2) $S \rightarrow AAS$ (3) $A \rightarrow SA$ (4) $A \rightarrow aa$. Which of the following productions denies the format of Chomsky Normal Form?**

a) 2,4

b) 1,3

c) 1, 2, 3, 4

d) 2,3,4

**Correct Answer:** a) 2,4

**Explanation:** Chomsky Normal Form requires right-hand productions to strictly be either exactly two non-terminals ($A \rightarrow BC$) or exactly one terminal ($A \rightarrow a$). Production 2 has three variables, and Production 4 has two terminals.

---

**47. What is the pumping length of string of length $x$?**

a) $x+1$

b) $x$

c) $x-1$

d) $x^2$

**Correct Answer:** a) $x+1$

**Explanation:** For finite regular languages inherently containing strings up to length $x$, theoretically setting the pumping length to $x+1$ ensures no string is long enough to trigger the lemma's conditions.

---

**48. The language of balanced paranthesis is:**

a) regular

b) non regular

c) may be regular

d) None of the mentioned

**Correct Answer:** b) non regular

**Explanation:** Balanced parentheses require infinite memory to dynamically keep count of open parentheses to ensure they eventually close, pushing it outside the capabilities of Finite Automata.

---

**49. Which of the problems are unsolvable?**

a) Halting problem

b) Boolean Satisfiability problem

c) Halting problem & Boolean Satisfiability problem

d) none of the mentioned

**Correct Answer:** a) Halting problem

**Explanation:** Alan Turing famously proved that the Halting Problem—creating a generalized algorithm to determine if any given arbitrary program will eventually halt—is mathematically undecidable.

---

**50. A language L is said to be ___ if there is a turing machine M such that $L(M) = L$ and M halts at every point.**

a) Turing acceptable

b) Decidable

c) Undecidable

d) None of the mentioned

**Correct Answer:** b) Decidable

**Explanation:** When a specific language has a Turing machine that successfully accepts correct strings AND guarantees to halt/reject incorrect strings without looping forever, the language is Decidable (Recursive).