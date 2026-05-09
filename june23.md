### **Data Structures & Algorithms**

**1. The worst case complexity of quick sort is**

a) $O(n)$

b) $O(\log n)$

c) $O(n^2)$

d) $O(n \log n)$

> **Answer:** c) $O(n^2)$
> **Explanation:** The worst-case scenario occurs when the pivot chosen is consistently the smallest or largest element (like in an already sorted array), leading to highly unbalanced partitions.

---

![alt text](image-3.png)

> **Answer:** d) 135531
> **Explanation:** The recursive function prints the current node, skips a node to call itself (start->next->next), and then prints the current node again as the recursion unwinds. This traces down as 1, 3, 5 and bubbles back up as 5, 3, 1.

---

**3. The prefix form of A-B/ (C D^E) is?***

a) -/*AACBDE

b) -ABCD*^DE

c) -A/B*C^DE

d) -A/BC*^DE

> **Answer:** c) -A/B*C^DE
> **Explanation:** Following standard order of operations (Exponentiation, Multiplication/Division, Addition/Subtraction) and converting strictly to prefix notation yields this result.

---

**4. Suppose we are sorting an array of eight integers using quicksort, and we have just finished the first partitioning with the array looking like this: 2 5 1 7 9 12 11 10. Which statement is correct?**

a) The pivot could be either the 7 or the 9.

b) The pivot could be the 7, but it is not the 9.

c) The pivot is not the 7, but it could be the 9.

d) Neither the 7 nor the 9 is the pivot.

> **Answer:** a) The pivot could be either the 7 or the 9.
> **Explanation:** After a partition, the pivot must sit exactly where it belongs in the final sorted array, with all smaller elements to its left and larger elements to its right. Both 7 and 9 meet this criteria in the given sequence.

---

**5. In a complete k-ary tree, every internal node has exactly k children or no child. The number of leaves in such a tree with n internal nodes is:**

a) nk

b) (n-1) k+1

c) $n(k-1)+1$

d) n(k-1)

> **Answer:** c) $n(k-1)+1$
> **Explanation:** Starting with the root (1 leaf), converting any leaf into an internal node adds $k$ new leaves but removes 1. Thus, each of the $n$ internal nodes yields a net gain of $(k-1)$ leaves.

---

**6. If a node in a Binary search tree has two children, then its inorder predecessor has**

a) No child

b) No left child

c) No right child

d) Two children

> **Answer:** c) No right child
> **Explanation:** The inorder predecessor is the maximum value located in the node's left subtree. If it possessed a right child, that child would hold a greater value, contradicting its status as the maximum.

---

**7. Using Bubble sort, the number of interchanges required to sort 5, 1, 6, 2 and 4 in ascending order is.**

a) 7

b) 5

c) 8

d) 6

> **Answer:** b) 5
> **Explanation:** The number of swaps in Bubble Sort matches the number of inversions (out-of-order pairs). There are 5 such pairs here: (5,1), (5,2), (5,4), (6,2), and (6,4).

---

**8. Which one of the following is a sequence container?**

a) stack

b) dequeue

c) queue

d) set

> **Answer:** b) dequeue
> **Explanation:** In C++, deque (double-ended queue) is a standard sequence container that stores elements linearly, whereas a set is associative, and stack/queue are considered container adaptors.

---

**9. Minimum number of queues needed to implement the priority queue is**

a) 1

b) 2

c) 3

d) 4

> **Answer:** b) 2
> **Explanation:** You need two standard queues: one to hold the main data elements and a secondary queue to temporarily store elements while positioning a newly inserted item according to its priority.

---

**10. The data structure used in breadth first search algorithm is**

a) queue

b) stack

c) heap

d) hash table

> **Answer:** a) queue
> **Explanation:** BFS explores a graph level by level. A queue's First-In-First-Out (FIFO) nature perfectly supports this by ensuring earlier discovered nodes are visited before deeper ones.

---

### **Operating Systems**

**11. Consider three CPU-intensive processes, which require 10, 20 and 30 time units and arrive at times 0, 2 and 6 respectively. How many context switches are needed if the operating system implements a shortest remaining time first scheduling algorithm? Do not count the context switches at time zero and at the end.**

a) 1

b) 2

c) 3

d) 4

> **Answer:** b) 2
> **Explanation:** Process 1 runs continuously from 0 to 10 because its remaining time is always shorter than the incoming processes. After it finishes, Process 2 runs to completion (context switch 1), followed by Process 3 (context switch 2).

---

**12. Which of the following are NOT shared by the threads of the same process?**

a) a and d

b) b and c

c) a and b

d) a, b and c

*(Note: Original options listed Stack, Registers, Address space, Message queue)*

> **Answer:** c) a and b
> **Explanation:** Threads within the same process share code, address space, and resources (like message queues), but they must maintain independent stacks and registers to track their unique execution flow.

---

**13. The problem of indefinite blockage of low priority jobs in general priority scheduling algorithm can be solved using**

a) Swapping

b) Dirty Bit

c) Aging

d) Compaction

> **Answer:** c) Aging
> **Explanation:** Aging resolves starvation by gradually increasing the priority of a process the longer it waits in the queue, ensuring it eventually gets CPU time.

---

**14. Which of the following are the advantage of Multiprogramming?**

a) High and efficient CPU utilization

b) CPU scheduling is not required

c) memory management is good

d) All of the above

> **Answer:** a) High and efficient CPU utilization
> **Explanation:** By keeping multiple jobs in memory, the OS can switch the CPU to another process whenever the current one is paused waiting for I/O, minimizing idle CPU time.

---

**15. A memory management system has 64 pages with 512 bytes page size. Physical memory consists of 32 page frames. Number of bits required in logical and physical address are respectively:**

a) 14 and 15

b) 14 and 29

c) 15 and 14

d) 16 and 32

> **Answer:** c) 15 and 14
> **Explanation:** 64 pages $\times$ 512 bytes = $2^6 \times 2^9 = 2^{15}$ bytes (15 logical bits). 32 frames $\times$ 512 bytes = $2^5 \times 2^9 = 2^{14}$ bytes (14 physical bits).

---

**16. Consider the reference string: 0 1 2 3 0 1 4 0 1 2 3 4. If FIFO page replacement algorithm is used, then the number of page faults with three page frames and four page frames are ___ and ___ respectively.**

a) 10, 9

b) 9, 9

c) 10, 10

d) 9, 10

> **Answer:** d) 9, 10
> **Explanation:** This is an illustration of Belady's Anomaly, where increasing the number of page frames from 3 to 4 paradoxically causes the number of FIFO page faults to increase from 9 to 10.

---

**17. Consider a disk queue with I/O requests on the following cylinders in their arriving order: 6,10,12,54,97,73,128,15,44,110,34,45. The disk head is assumed to be at cylinder 23 and moving in the direction of decreasing number of cylinders. Total number of cylinders in the disk is 150. The disk head movement using SCAN-scheduling algorithm is:**

a) 172

b) 173

c) 151

d) 161

> **Answer:** c) 151
> **Explanation:** The head moves from 23 down to 0 (distance of 23), then reverses direction and sweeps up to the highest request at 128 (distance of 128). $23 + 128 = 151$.

---

**18. At a particular time of computation, the value of a counting semaphore is 10. Then 12 P operations and "x" V operations were performed on this semaphore. If the final value of semaphore is 7, x will be**

a) 8

b) 9

c) 10

d) 11

> **Answer:** b) 9
> **Explanation:** P operations decrement the semaphore; V operations increment it. $10 - 12 + x = 7$, which simplifies to $-2 + x = 7$, meaning $x = 9$.

---

**19. In the ___ algorithm, the disk head moves from one end to the other, servicing requests along the way. When the head reaches the other end, it immediately returns to the beginning of the disk without servicing any requests on the return trip.**

a) LOOK

b) SCAN

c) C-SCAN

d) C-LOOK

> **Answer:** c) C-SCAN
> **Explanation:** Circular-SCAN provides a more uniform wait time by treating the cylinders as a continuous circle, jumping back to the start entirely to resume sweeping in the same direction.

---

**20. Paging suffers from ___ fragmentation.**

a) External

b) Internal

c) Physical

d) All of the above

> **Answer:** b) Internal
> **Explanation:** Paging perfectly prevents external fragmentation because free frames can be anywhere. However, if a process's memory requirement isn't an exact multiple of the page size, the leftover space in the final frame creates internal fragmentation.

---

### **Computer Organization & Architecture**

**21. The main virtue for using single Bus structure is**

a) Fast data transfers

b) Cost effective connectivity

c) Cost effective connectivity and ease of attaching peripheral devices

d) None of the mentioned

> **Answer:** c) Cost effective connectivity and ease of attaching peripheral devices
> **Explanation:** A single system bus is simple and inexpensive to build, and it allows new peripherals to be easily connected without needing dedicated independent data pathways.

---

**22. Memory Buffer Register (MBR) is connected to**

a) Control Bus

b) Address Bus

c) Data Bus

d) System Bus

> **Answer:** c) Data Bus
> **Explanation:** The MBR (or Memory Data Register) acts as a gateway for all data moving in and out of the CPU to the main memory, traveling directly across the Data Bus.

---

**23. The basic component of arithmetic circuit is**

a) parallel subtractor.

b) parallel adder.

c) half adder.

d) full adder.

> **Answer:** b) parallel adder.
> **Explanation:** A parallel adder is the foundation of the Arithmetic Logic Unit (ALU), allowing the processor to perform multi-bit binary addition simultaneously.

---

**24. When we use auto increment or auto decrements, which of the following is/are true?**

a) 1, 2, 3

b) 2

c) 1, 3

d) 2, 3

*(Note: Original statements discussed whether addresses/operands are altered and retrieved first)*

> **Answer:** d) 2, 3
> **Explanation:** In auto-increment, the current pointer value is used to fetch the operand first, and then the register is updated. These modes apply readily to general-purpose registers acting as memory pointers.

---

**25. When we perform subtraction on -7 and -5 the answer in 2's complement form is**

a) 11110

b) 1110

c) 1010

d) 0010

> **Answer:** b) 1110
> **Explanation:** Calculating $-7 - (-5)$ results in $-2$. In 4-bit 2's complement notation, positive 2 is 0010. Inverting the bits (1101) and adding 1 gives -2 as 1110.

---

**26. The instruction -> Add LOCA, R0 does**

a) Adds the value of LOCA to R0 and stores in the temp register

b) Adds the value of R0 to the address of LOCA

c) Adds the values of both LOCA and R0 and stores it in R0

d) Adds the value of LOCA with a value in accumulator and stores it in R0

> **Answer:** c) Adds the values of both LOCA and R0 and stores it in R0
> **Explanation:** This is standard assembly syntax where the contents at memory location LOCA are fetched, added to the current value of Register 0, and the sum overwrites R0.

---

**27. Suppose, after analyzing a new cache design, you discover that the cache has far too many conflict misses, and this needs to be resolved. You know that you must increase associativity in order to decrease the number of cache misses. What are the implications of increasing associativity?**

a) Slower cache access time

b) Increase index bits

c) Increase block size

d) All of these

> **Answer:** a) Slower cache access time
> **Explanation:** Increasing associativity reduces conflict misses but requires more complex multiplexing hardware to search multiple lines in parallel, which inevitably slightly slows down the physical hit time.

---

**28. In a k-way set associative cache, the cache is divided into v sets, each of which consists of k lines. The main memory block numbered j must be mapped to any one of the cache lines from...**

a) (j mod v) * k to (j mod v) * k + (k-1)

b) (j mod v) to (j mod v) + (k-1)

c) (j mod k) to (j mod k) + (v-1)

d) (j mod k) * v to (j mod k) * v + (v-1)

> **Answer:** a) (j mod v) * k to (j mod v) * k + (k-1)
> **Explanation:** The block first maps to a specific set using j mod v. Since each set contains k lines sequentially, the actual physical line indices span from the start of that set to its end.

---

**29. Highly encoded schemes that use compact codes to specify a small number of functions in each micro instruction is**

a) Horizontal organisation

b) Vertical organisation

c) Diagonal organisation

d) None of the mentioned

> **Answer:** b) Vertical organisation
> **Explanation:** Vertical microprogramming uses tightly encoded control words to save memory space, requiring a decoder to translate the bits into actual control signals, unlike horizontal which uses longer, unencoded bits.

---

**30. DMA interface unit eliminates the need to use CPU registers to transfers data from**

a) MAR to MBR

b) MBR to MAR

c) I/O units to memory

d) Memory to I/O units

> **Answer:** d) Memory to I/O units
> **Explanation:** Direct Memory Access (DMA) allows hardware subsystems to access main system memory for reading/writing independently of the central processing unit, freeing up the CPU.

---

### **Database Management Systems**

**31. Let E1 and E2 be two entities in an E/R diagram with simple single-valued attributes. R1 and R2 are two relationships between E1 and E2, where R1 is one-to-many and R2 is many-to-many. R1 and R2 do not have any attributes of their own. What is the minimum number of tables required to represent this situation in the relational model?**

a) 2

b) 3

c) 4

d) 5

> **Answer:** b) 3
> **Explanation:** You need one table for E1, one for E2, and a third for the many-to-many relationship (R2). The one-to-many relationship (R1) can be collapsed directly into E2's table as a foreign key, so it doesn't need its own table.

---

**32. Consider the join of a relation R with relation S. If R has m tuples and S has n tuples, then the maximum size of join is............**

a) mn

b) m+n

c) $(m+n)/2$

d) 2(m+n)

> **Answer:** a) mn
> **Explanation:** In the absolute worst-case scenario (like a Cartesian cross product where every row matches every other row), the resulting join will contain every combination of tuples: $m \times n$.

---

**33. An index record appears for every search key value in the file**

a) Dense index

b) Sparse index

c) Hash index

d) Single-key index

> **Answer:** a) Dense index
> **Explanation:** By definition, a dense index maintains an index entry for every single search key value found in the data file, making lookups fast but requiring more storage.

---

**34. If a relation is in BCNF Then it is in:**

a) 2 NF

b) 3 NF

c) 1 NF

d) 1 NF and 2 NF

> **Answer:** b) 3 NF
> **Explanation:** BCNF (Boyce-Codd Normal Form) is a stricter version of 3NF. Because normal forms build on each other, any relation that has reached BCNF is guaranteed to already satisfy the rules of 3NF (as well as 2NF and 1NF).

---

**35. Which of the following is a DDL command?**

a) Select

b) Create

c) Insert

d) Delete

> **Answer:** b) Create
> **Explanation:** Data Definition Language (DDL) commands define the database structure or schema. CREATE builds tables, whereas SELECT, INSERT, and DELETE are Data Manipulation Language (DML) commands used for the data inside.

---

**36. The number of attributes in a relation is called its**

a) cardinality

b) size

c) schema

d) degree

> **Answer:** d) degree
> **Explanation:** In relational database terminology, the "degree" (or arity) refers to the number of columns (attributes) a table has, while "cardinality" refers to the number of rows (tuples).

---

**37. Consider a database implemented using B+ tree for file indexing and installed on a disk drive with block size of 4 KB. The size of search key is 12 bytes and the size of tree/disk pointer is 8 bytes. Assume that the database has one million records. The minimum number of disk accesses required to retrieve any record in the database is:**

a) 1

b) 2

c) 3

d) 4

> **Answer:** d) 4
> **Explanation:** Given the block size and key/pointer sizes, the tree's order (branching factor) is approximately 200. With 1 million records, a balanced tree of this capacity requires a depth of 3 for the index blocks, plus 1 final access to grab the actual data block.

---

**38. Consider the relation R(A,B,C,D,E) and the set F={AB->CE, E->AB, C->D}. What is the highest normal form of this relation?**

a) 1 NF

b) 2 NF

c) 3 NF

d) BCNF

> **Answer:** b) 2 NF
> **Explanation:** The candidate keys are AB and E. The dependency C->D represents a transitive dependency (a non-prime attribute determining another non-prime attribute), which violates 3NF, locking the relation at 2NF.

---

**39. What is the Lost Update Problem also known as?**

a) W-W Conflict

b) W-R Conflict

c) R-R Conflict

d) None

> **Answer:** a) W-W Conflict
> **Explanation:** A lost update happens when two concurrent transactions attempt to write to the same data item simultaneously (Write-Write), causing one transaction's update to blindly overwrite and erase the other's.

---

**40. Consider the following transactions with data items P and Q initialized to zero: T1 reads P and writes Q; T2 reads Q and writes P. Any non-serial interleaving of T1 and T2 for concurrent execution leads to:**

a) A serializable schedule

b) A schedule that is not conflict serializable

c) A conflict serializable schedule

d) A schedule for which a precedence graph cannot be drawn

> **Answer:** b) A schedule that is not conflict serializable
> **Explanation:** Because T1 reads what T2 writes and T2 reads what T1 writes, interleaving them creates a cycle in their dependency (precedence) graph, making it impossible to conflict-serialize.

---

### **Theory of Computation**

**41. The non-Kleene Star operation accepts the following string of finite length over set $A=\{0,1\}$ where string s contains even number of 0 and 1:**

a) 01,0011, 010101

b) 0011, 11001100

c) ε, 0011, 11001100

d) ε, 0011, 11001100

> **Answer:** b) 0011, 11001100
> **Explanation:** The "non-Kleene star" implies positive closure ($+$), which requires at least one instance to occur, thereby explicitly excluding the empty string ($\epsilon$) that a standard Kleene star would permit.

---

**42. Which of the following is a not a part of 5-tuple finite automata:**

a) Input alphabet

b) Transition function

c) Initial State

d) Output Alphabet

> **Answer:** d) Output Alphabet
> **Explanation:** A standard Finite Automaton (like a DFA or NFA) is defined strictly as an acceptor (States, Alphabet, Transitions, Start State, Accept States). Machines with output alphabets are transducers (Moore/Mealy machines).

---

**43. Which of the following conversion is not possible (algorithmically)?**

a) Regular grammar to CFG

b) Non Deterministic FA to Deterministic FA

c) Non Deterministic PDA to Deterministic PDA

d) Non Deterministic TM to Deterministic TM

> **Answer:** c) Non Deterministic PDA to Deterministic PDA
> **Explanation:** While NFAs can always convert to DFAs, Non-Deterministic Pushdown Automata (NPDAs) are strictly more powerful than Deterministic PDAs. Some languages can only be accepted non-deterministically.

---

**44. Regular expression for all strings starts with ab and ends with bba is........**

a) $aba^*b^*bba$

b) $ab(ab)^*bba$

c) $ab(a+b)^*bba$

d) All of the mentioned

> **Answer:** c) $ab(a+b)^*bba$
> **Explanation:** The expression explicitly anchors ab at the beginning and bba at the end, while (a+b)* allows absolutely any combination of a's and b's of any length in the middle.

---

**45. Pumping lemma is generally used for proving that**

a) Given grammar is regular

b) Given grammar is not regular

c) Whether two given regular expressions are equivalent or not

d) None of these

> **Answer:** b) Given grammar is not regular
> **Explanation:** The Pumping Lemma states a property that all regular languages must have. It cannot prove a language is regular, but it is heavily used via contradiction to prove that a language is not regular.

---

**46. Consider the regular language $L=(111+11111)^*$. The minimum number of states in any DFA accepting this language is**

a) 3

b) 5

c) 8

d) 9

> **Answer:** d) 9
> **Explanation:** This acts like the Frobenius coin problem. The largest unformable combination of 3s and 5s is $(3 \times 5) - 3 - 5 = 7$. The DFA needs 9 states (spanning 0 through 8) to successfully track string lengths past this threshold.

---

**47. Suppose a regular language L is closed under the operation halving, then the result would be**

a) 1/4 L will be regular

b) 1/2 L will be regular

c) 1/8 L will be regular

d) All of the mentioned

> **Answer:** d) All of the mentioned
> **Explanation:** Regular languages are closed under the "half" operation. Because applying the operation yields another regular language, you can chain the operation recursively to achieve 1/4, 1/8, etc.

---

**48. Which among the following cannot be accepted by a regular grammar?**

a) L is a set of numbers divisible by 2

b) L is a set of binary complement

c) L is a set of string with odd number of 0

d) L is a set of $0^n 1^n$

> **Answer:** d) L is a set of $0^n 1^n$
> **Explanation:** The language $0^n 1^n$ requires the automaton to count the exact number of 0s to match them against the 1s. Regular grammars (and Finite Automata) lack the unbounded memory (like a stack) necessary to perform this counting.

---

**49. If L1 and L2 are context free languages, which of the following is context free?**

a) $L1^*$

b) L2UL1

c) L1.L2

d) All of the mentioned

> **Answer:** d) All of the mentioned
> **Explanation:** Context-free languages are mathematically proven to be closed under the regular operations of Union (U), Concatenation (.), and the Kleene Star (*).

---

**50. Consider a grammar with the following productions: S--> aab | bac | aB, S-->aS | b, S --> abb | ab, S a --> bdb. The above grammar is:**

a) Context free

b) Regular

c) Context sensitive

d) Type 0

> **Answer:** c) Context sensitive
> **Explanation:** The production rule S a --> bdb violates context-free rules because the left-hand side contains more than a single non-terminal. Since the left side is shorter than or equal to the right side, it qualifies as a Context-Sensitive Grammar (Type 1).