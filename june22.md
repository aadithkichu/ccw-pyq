Here is the complete and neatly formatted set of questions (1 through 50) from your provided list, with double spacing before and after every option to ensure perfectly clear rendering in Markdown.

**1. The Inorder and Preorder traversal of a binary tree is dbeafcg and abdecfg respectively. Which among the following is the correct Post Order Traversal Sequence for this tree?**

a) debfgca

b) edbgfca

c) edbfgca

d) defgbca

**Correct Answer:** a) debfgca

**Explanation:** The first element in a preorder sequence (a) is always the root. Looking at the inorder sequence, elements to the left of a (dbe) form the left subtree, and elements to the right (fcg) form the right subtree. Processing these subtrees recursively in a Left-Right-Root manner yields the postorder sequence debfgca.

---

**2. Which of the following is not the application of stack?**

a) A parenthesis balancing program

b) Tracking of local variables at run time

c) Compiler Syntax Analyzer

d) Data Transfer between two asynchronous processes

**Correct Answer:** d) Data Transfer between two asynchronous processes

**Explanation:** Data transfer between asynchronous processes typically utilizes a Queue (acting as a FIFO buffer) rather than a Stack (LIFO), to ensure that the data is processed in the order it was received.

---

**3. In the worst case, the number of comparisons needed to search a singly linked list of length $n$ for a given element is?**

a) $\log_2 n$

b) $\frac{n}{2}$

c) $\log_2 n-1$

d) $n$

**Correct Answer:** d) $n$

**Explanation:** In the worst-case scenario (the element is at the very end of the list or not present at all), you must traverse every single node in the linked list, resulting in $n$ comparisons.

---

**4. To implement a stack using queue (with only enqueue and dequeue operations), how many queues will you need?**

a) 1

b) 2

c) 3

d) 4

**Correct Answer:** b) 2

**Explanation:** Simulating the Last-In-First-Out (LIFO) behavior of a stack using First-In-First-Out (FIFO) queues standardly requires two queues to temporarily hold elements while reordering them during push or pop operations.

---

**5. The optimal data structure used to solve Tower of Hanoi is**

a) Tree

b) Heap

c) Priority queue

d) Stack

**Correct Answer:** d) Stack

**Explanation:** The Tower of Hanoi is a classic recursive problem. Recursive function calls inherently use the system's call stack to pause current execution states, making a Stack the natural data structure for solving it.

---

**6. Assume that the operators +, -, X are left associative and ^ is right associative. The order of precedence (from highest to lowest) is ^, X, +, -. The postfix expression for the infix expression $a+b\ X\ c-d^{\wedge}e^{\wedge}f$ is?**

a) abc X+ def ^^ -

b) abc $X+de^{\wedge}f^{\wedge}-$

c) $ab+c~Xd-e^{\wedge}f^{\wedge}$

d) -+aXbc^ ^def

**Correct Answer:** a) abc X+ def ^^ -

**Explanation:** Due to the right-associativity of the exponential operator ^, the sub-expression $e^{\wedge}f$ is evaluated first, followed by $d^{\wedge}(e^{\wedge}f)$. The multiplication X is evaluated next, followed by addition and then subtraction, resulting in this specific postfix form.

---

**7. The time complexity of heap sort in worst case is**

a) $O(\log n)$

b) $O(n)$

c) $O(n \log n)$

d) $O(n^2)$

**Correct Answer:** c) $O(n \log n)$

**Explanation:** Heap sort guarantees $O(n\log n)$ performance because building the initial max-heap takes $O(n)$ time, and extracting the $n$ elements one by one takes $O(\log n)$ time per extraction.

---

**8. Suppose we are sorting an array of eight integers using heapsort, and we have just finished some heapify (either maxheapify or minheapify) operations. The array now looks like this: 16 14 15 10 12 27 28. How many heapify operations have been performed on root of heap?**

a) 1

b) 2

c) 3 or 4

d) 5 or 6

**Correct Answer:** b) 2

**Explanation:** The elements 27 and 28 are the two largest numbers and are correctly placed at the end of the array. This indicates that the max element was extracted and the root was heapified twice.

---

**9. What is the number of edges present in a complete graph having $n$ vertices?**

a) $\frac{n(n+1)}{2}$

b) $\frac{n(n-1)}{2}$

c) $n$

d) Information given is insufficient

**Correct Answer:** b) $\frac{n(n-1)}{2}$

**Explanation:** In a complete graph, every vertex is connected to every other vertex exactly once. This is a combinatorial problem of choosing 2 vertices from $n$ available, which evaluates to $\frac{n(n-1)}{2}$.

---

**10. If several elements are competing for the same bucket in the hash table, what is it called?**

a) Diffusion

b) Replication

c) Collision

d) Duplication

**Correct Answer:** c) Collision

**Explanation:** When a hash function maps two or more distinct keys to the exact same index (or bucket) in a hash table, the resulting conflict is termed a collision.

---

**11. A process which is copied from main memory to secondary memory on the basis of requirement is known as**

a) Demand paging

b) Paging

c) Threads

d) Segmentation

**Correct Answer:** a) Demand paging

**Explanation:** Demand paging is a memory management technique where pages are only loaded into main memory from the disk when a program actively accesses them (i.e., on demand).

---

**12. For which of the following purposes, Banker's algorithm is used?**

a) Preventing deadlock

b) Solving deadlock

c) Recover from deadlock

d) None

**Correct Answer:** a) Preventing deadlock

**Explanation:** The Banker's algorithm is a resource allocation and deadlock avoidance algorithm. By simulating the allocation of predetermined maximum possible amounts of all resources, it checks for safe states, thus effectively preventing the system from ever entering a deadlock state.

---

**13. Identify the system calls that on termination does not return control to the calling point.**

a) exec

b) fork

c) longjmp

d) ioctl

**Correct Answer:** a) exec

**Explanation:** The exec family of system calls replaces the current running process image entirely with a new process image. Because the original program is overwritten, a successful exec call never returns to the point where it was called.

---

**14. A CPU generates 32-bit virtual addresses. The page size is 4 KB. The processor has a translation look-aside buffer (TLB) which can hold a total of 128-page table entries and is 4-way set associative. The minimum size of the TLB tag is**

a) 11 bits

b) 13 bits

c) 15 bits

d) 20 bits

**Correct Answer:** c) 15 bits

**Explanation:** For a 4 KB ($2^{12}$ bytes) page size, the offset requires 12 bits. The Virtual Page Number (VPN) is $32 - 12 = 20$ bits. The TLB holds 128 entries and is 4-way set associative, meaning there are $128 / 4 = 32$ sets ($2^5$), which requires 5 bits for the TLB index. The TLB tag is the remaining part of the VPN, so $20 \text{ bits (VPN)} - 5 \text{ bits (Index)} = 15$ bits.

---

**15. Dirty bit is used to indicate which of the following?**

a) A page fault has occurred

b) A page has corrupted data

c) A page has been modified after being loaded into cache

d) An illegal access of page

**Correct Answer:** c) A page has been modified after being loaded into cache

**Explanation:** A dirty bit (or modified bit) is a flag used in page tables to track whether a page's contents have been written to or altered since it was loaded from secondary storage. If the bit is set, the OS knows it must write the updated page back to disk before replacing it in memory.

---

**16. A system uses FIFO policy for page replacement. It has 4-page frames with no pages loaded to begin with. The system first accesses 100 distinct pages in some order and then accesses the same 100 pages but now in the reverse order. How many page faults will occur?**

a) 196

b) 192

c) 197

d) 195

**Correct Answer:** a) 196

**Explanation:** For the first 100 distinct page accesses, every single access will cause a page fault (100 faults). At the end of this sequence, the memory holds the last 4 pages accessed (pages 97, 98, 99, 100). When accessing the pages in reverse order, the first 4 pages requested are already in memory, resulting in hits. The remaining 96 accesses will each cause a new page fault. Total faults = $100 + 96 = 196$.

---

**17. If a process is executing in its critical section, then no other processes can be executing in their critical section. What is this condition called?**

a) mutual exclusion

b) critical exclusion

c) synchronous exclusion

d) asynchronous exclusion

**Correct Answer:** a) mutual exclusion

**Explanation:** Mutual exclusion is the fundamental requirement for solving the critical section problem in operating systems, ensuring that only one process or thread can access shared resources or critical code segments concurrently.

---

**18. What is a long-term scheduler?**

a) It selects processes which have to be brought into the ready queue

b) It selects processes which have to be executed next and allocates CPU

c) It selects processes which heave to remove from memory by swapping

d) None of the mentioned

**Correct Answer:** a) It selects processes which have to be brought into the ready queue

**Explanation:** The long-term scheduler (also known as the job scheduler) controls the degree of multiprogramming by deciding which processes from the mass-storage pool are admitted into main memory (the ready queue) to compete for CPU time.

---

**19. A systematic procedure for moving the CPU to new process is known as-**

a) Synchronization

b) Deadlock

c) Starvation

d) Context Switching

**Correct Answer:** d) Context Switching

**Explanation:** Context switching involves saving the current state (context) of a running process so that it can be restored later, and loading the saved state of a new process so execution can transition smoothly.

---

**20. In a virtual memory system, size of virtual address is 32-bit, size of physical address is 30-bit, page size is 4 Kbyte and size of each page table entry is 32-bit. The main memory is byte addressable. Which one of the following is the maximum number of bits that can be used for storing protection and other information in each page table entry?**

a) 2

b) 10

c) 12

d) 14

**Correct Answer:** d) 14

**Explanation:** A 4 Kbyte page size requires 12 bits for the offset ($2^{12}$). The physical address is 30 bits, meaning the physical frame number takes $30 - 12 = 18$ bits. Since the total Page Table Entry (PTE) size is 32 bits, the remaining bits available for protection flags and other info is $32 - 18 = 14$ bits.

---

**21. The amount of ROM needed to implement a 4-bit multiplier is**

a) 64 bits

b) 128 bits

c) 1 Kbits

d) 2 Kbits

**Correct Answer:** d) 2 Kbits

**Explanation:** A 4-bit multiplier takes two 4-bit numbers as inputs, equating to an 8-bit input address line. This yields $2^8 = 256$ memory locations. Multiplying two 4-bit numbers (max $15 \times 15 = 225$) requires an 8-bit output. Total ROM required is $256 \text{ words} \times 8 \text{ bits/word} = 2048 \text{ bits}$, which is 2 Kbits.

---

![](Screenshot_20260509_125646_Drive.jpg)


**Correct Answer:** a) a6 b1 c3 d5 e2 f4

**Explanation:** Immediate mode maps to Constant Operands (a-6); Direct mode accesses fixed memory locations like Local variables (b-1); Indirect mode is inherently used for Pointers (c-3); Index addressing is standard for iterating through Arrays (d-5); Base addressing enables Relocatable programs (e-2); and Relative addressing takes advantage of Branching and Locality of reference (f-4).

---

**23. Register renaming is done in pipelined processors**

a) as an alternative to register allocation at compile time

b) for efficient access to function parameters and local variables

c) to handle certain kinds of hazards

d) as part of address translation

**Correct Answer:** c) to handle certain kinds of hazards

**Explanation:** Register renaming is a technique used by out-of-order execution processors to avoid false data dependencies (specifically Write-After-Write and Write-After-Read hazards), enabling more instructions to be executed in parallel.

---

**24. Memory interleaving is done to**

a) Increase the amount of logical memory

b) Reduce memory access time

c) Simplify memory interfacing

d) Reduce page faults

**Correct Answer:** b) Reduce memory access time

**Explanation:** Memory interleaving distributes sequential memory addresses across multiple memory banks. Because these banks can process requests concurrently, the CPU doesn't have to wait for one operation to finish before starting the next, effectively hiding memory latency and reducing overall access time.

---

**25. In an instruction execution pipeline, the earliest that the data TLB (Translation Lookaside Buffer) can be accessed is**

a) before effective address calculation

b) during effective address calculation

c) after effective address calculation has started

d) after data address calculation has completed

**Correct Answer:** d) after effective address calculation has completed

**Explanation:** The TLB is hardware that translates a virtual address to a physical address. Therefore, the processor must first finish calculating the virtual (effective) address before it can query the TLB for its physical mapping.

---

![](Screenshot_20260509_131651_Drive.jpg)

**Correct Answer:** b) A2B1C3D4

**Explanation:** Direct Memory Access (DMA) is suited for high-speed block data transfers typical of a Disk (A-2). Cache memory utilizes High-speed RAM (B-1). Interrupt-driven I/O is commonly used for slower, character-based devices like a Printer (C-3). The Condition Code Register stores status flags generated by ALU operations (D-4).

---

**27. The technique whereby the DMA controller steals the access cycles of the processor to operate is called**

a) Fast Conning

b) Memory Con

c) Cycle Stealing

d) Memory Stealing

**Correct Answer:** c) Cycle Stealing

**Explanation:** Cycle stealing allows the DMA controller to transfer data on the system bus by pausing the CPU for exactly one bus cycle. It "steals" this cycle to securely transfer data without triggering a full context switch.

---

**28. For the daisy chain scheme of connecting I/O devices, which of the following statement is true?**

a) It gives non-uniform priority to various devices

b) It is only useful for connecting slow devices to a processor

c) It requires a separate interrupt pin on the processor for each device

d) It gives uniform priority to all devices

**Correct Answer:** a) It gives non-uniform priority to various devices

**Explanation:** In a daisy chain configuration, hardware devices are connected sequentially. The priority of a device is determined by its physical proximity to the CPU; the first device in the chain intercepts the interrupt acknowledge signal first, creating a non-uniform, strict priority hierarchy.

---

**29. A machine with $N$ different opcodes can contain how many different sequences of micro-operations**

a) $2^N$

b) $N^N$

c) $N^2$

d) $N$

**Correct Answer:** d) $N$

**Explanation:** Every distinct machine-level opcode is defined by a unique microprogram (a specific sequence of micro-operations) hardwired or stored in control memory. Therefore, $N$ opcodes directly map to $N$ sequences.

---

**30. A cache has a 64 KB capacity, 128-byte lines (blocks), and is 4-way set associative. The system containing the cache uses 32-bit addresses. How many lines (blocks) and sets does the cache have?**

a) 64

b) 128

c) 256

d) 32

**Correct Answer:** b) 128 (Sets)

**Explanation:** First, find the total number of blocks (lines): $64 \text{ KB} / 128 \text{ Bytes} = 512$ total blocks. Because it is 4-way set associative, these blocks are grouped into sets of 4. Total sets = $512 / 4 = 128$ sets.

---

**31. Which of the following is the property of transaction that protects data from system failure?**

a) Atomicity

b) Isolation

c) Durability

d) Consistency

**Correct Answer:** c) Durability

**Explanation:** Durability guarantees that once a transaction completes successfully (commits), its updates survive system crashes, power losses, or other subsequent failures, usually by recording operations in a non-volatile transaction log.

---

**32. Which normalization form is based on the transitive dependency?**

a) 1NF

b) 2NF

c) 3NF

d) BCNF

**Correct Answer:** c) 3NF

**Explanation:** Third Normal Form (3NF) dictates that a relation must already be in 2NF, and no non-prime attribute is transitively dependent on the primary key.

---

**33. Which of the following SQL command is used for removing (or deleting) a relation form the database?**

a) Drop

b) Delete

c) Rollback

d) Remove

**Correct Answer:** a) Drop

**Explanation:** `DROP` is a Data Definition Language (DDL) command that permanently deletes a table's entire schema structure and data from the database. `DELETE` is a Data Manipulation Language (DML) command that only removes rows from an existing table.

---

**34. Which of the following is known as minimal super key?**

a) Primary key

b) Candidate key

c) Foreign key

d) None

**Correct Answer:** b) Candidate key

**Explanation:** A candidate key is a subset of a super key where no proper subset of those attributes can uniquely identify a tuple. Hence, it is defined as a minimal super key.

---

**35. Given the following relation instance.  
x y z  
1 4 2  
1 5 3  
1 6 3  
3 2 2  
Which of the following functional dependencies are satisfied by the instance?**

a) $XY \rightarrow Z$ and $Z \rightarrow Y$

b) $YZ \rightarrow X$ and $Y \rightarrow Z$

c) $YZ \rightarrow X$ and $X \rightarrow Z$

d) $XZ \rightarrow Y$ and $Y \rightarrow X$

**Correct Answer:** b) $YZ \rightarrow X$ and $Y \rightarrow Z$

**Explanation:** Looking at the column for `y`, all values (4, 5, 6, 2) are unique. Because every value of `y` is completely unique, `y` functionally determines all other attributes trivially. Therefore, $Y \rightarrow Z$ is valid, and consequently, $YZ \rightarrow X$ is also valid.

---

**36. Consider a relational schema with Suppliers, Parts, and Catalog. Consider a query:
`SELECT S.sname FROM Suppliers S WHERE S.sid NOT IN (SELECT C.sid FROM Catalog C WHERE C.pid IN (SELECT P.pid FROM Parts P WHERE P.color <> 'blue'))`
Which one of the following is the correct interpretation of the above query**

a) Find the names of all suppliers who have supplied a non-blue part.

b) Find the names of all suppliers who have not supplied a non-blue part.

c) Find the names of all suppliers who have supplied only blue parts.

d) Find the names of all suppliers who have not supplied only blue parts.

**Correct Answer:** b) Find the names of all suppliers who have not supplied a non-blue part.

**Explanation:** The innermost query pulls IDs for parts that are NOT blue. The middle query pulls the supplier IDs of those who supply those non-blue parts. The outermost query excludes those suppliers. What remains are the suppliers who exclusively supply blue parts, which mathematically means they have *not* supplied a non-blue part.

---

**37. An entity in A is associated with at most one entity in B. An entity in B, however, can be associated with any number (zero or more) of entities in A.**

a) One-to-many

b) One-to-one

c) Many-to-many

d) Many-to-one

**Correct Answer:** d) Many-to-one

**Explanation:** Because multiple instances of entity A can point to a single instance of entity B, but one instance of A points to a maximum of one B, the mapping relationship direction from A to B is defined as Many-to-One.

---

**38. Which commands are used to control access over objects in relational database?**

a) CASCADE & MVD

b) GRANT & REVOKE

c) QUE & QUIST

d) None of these

**Correct Answer:** b) GRANT & REVOKE

**Explanation:** Data Control Language (DCL) utilizes `GRANT` to assign access privileges to database users and `REVOKE` to withdraw those permissions.

---

**39. Consider ORACLE relationships: One (x, y) = {<2, 5>, <1, 6>, <1, 6>, <1, 6>, <4, 8>, <4, 8>} and Two (x, y) = {<2, 55>, <1, 1>, <4, 4>, <1, 6>, <4, 8>, <4, 8>, <9, 9>, <1, 6>}.
SQ1: `SELECT * FROM One EXCEPT (SELECT * FROM Two)`
SQ2: `SELECT * FROM One EXCEPT ALL (SELECT * FROM Two)`
What is the cardinality of the result generated on the execution of each SQL query?**

a) 2 and 1, respectively

b) 1 and 2, respectively

c) 2 and 2, respectively

d) 1 and 1, respectively

**Correct Answer:** b) 1 and 2, respectively

**Explanation:** `EXCEPT` performs standard set difference, eliminating duplicates first. Distinct `One` = {<2,5>, <1,6>, <4,8>}. Distinct `Two` = {<2,55>, <1,1>, <4,4>, <1,6>, <4,8>, <9,9>}. The difference is just {<2,5>} (cardinality 1). `EXCEPT ALL` retains duplicates (multiset difference). For <1,6>, 3 occurrences in One minus 2 in Two leaves 1 occurrence. For <4,8>, 2 minus 2 leaves 0. For <2,5>, 1 minus 0 leaves 1. The result is {<1,6>, <2,5>} (cardinality 2).

---

**40. Which of the following is TRUE?**

a) Every relation in 3NF is also in BCNF

b) A relation R is in 3NF if every non-prime attribute of R is fully functionally dependent on every key of R

c) Every relation in BCNF is also in 3NF

d) No relation can be in both BCNF and 3NF

**Correct Answer:** c) Every relation in BCNF is also in 3NF

**Explanation:** Boyce-Codd Normal Form (BCNF) is a more restrictive extension of the Third Normal Form (3NF). A relation must strictly satisfy all conditions of 3NF before it can be considered for BCNF.

---

**41. A Language for which no DFA exist is a**

a) Regular Language

b) Non-Regular Language

c) May be Regular

d) Cannot be said

**Correct Answer:** b) Non-Regular Language

**Explanation:** Kleene's Theorem establishes that the class of languages recognized by Deterministic Finite Automata (DFAs) is exactly identical to the class of regular languages. If a language cannot be mapped to a DFA, it is inherently non-regular.

---

![alt text](image.png)

**Correct Answer:** a) $\epsilon$

**Explanation:** Based on the standard state diagram for this question, the initial state ($q_1$) is not an accepting state. Because the empty string ($\epsilon$) requires zero transitions, the automaton halts in $q_1$ and rejects the input.

---

**43. Regular expression for all strings starts with ab and ends with bba is.**

a) $aba^{*}b^{*}bba$

b) $ab(ab)^{*}bba$

c) $ab(a+b)^{*}bba$

d) String of letter count 11

**Correct Answer:** c) $ab(a+b)^{*}bba$

**Explanation:** The expression mandates the exact prefix `ab` and the exact suffix `bba`. The middle portion $(a+b)^{*}$ correctly represents the Kleene closure, allowing any possible string combination of 'a's and 'b's to exist between the prefix and suffix.

---

**44. Which of the following options is correct?
Statement 1: Initial State of NFA is Initial State of DFA.
Statement 2: The final state of DFA will be every combination of final state of NFA.**

a) Statement 1 is true and Statement 2 is true

b) Statement 1 is true and Statement 2 is false

c) Statement 1 can be true and Statement 2 is true

d) Statement 1 is false and Statement 2 is also false

**Correct Answer:** a) Statement 1 is true and Statement 2 is true

**Explanation:** During Subset Construction, the initial state of the DFA is derived directly from the initial state of the NFA (specifically its $\epsilon$-closure). Furthermore, any subset (state in the DFA) that contains at least one accepting state from the NFA becomes a final state in the DFA.

---

**45. The number of elements present in the $\epsilon$-closure(f2) in the given diagram: (Diagram features an epsilon transition from f2 to f3)**

![alt text](image-1.png)

**Correct Answer:** c) 2

**Explanation:** The $\epsilon$-closure of a state includes the state itself, plus any states reachable exclusively by following $\epsilon$-transitions. Based on the graph, from node $f_2$, you can traverse an $\epsilon$-transition to $f_3$, making the closure set $\{f_2, f_3\}$, which contains exactly 2 elements.

---

**46. The language accepted by Push down Automaton:**

a) Recursive Language

b) Context free language

c) Linearly Bounded language

d) All of the mentioned

**Correct Answer:** b) Context free language

**Explanation:** A Pushdown Automaton (PDA) is defined as a finite automaton equipped with stack memory. This architecture provides precisely the computational power needed to recognize Context-Free Languages (CFLs).

---

**47. Given grammar G:
(1) $S \rightarrow AS$ (2) $S \rightarrow AAS$ (3) $A \rightarrow SA$ (4) $A \rightarrow aa$
Which of the following productions denies the format of Chomsky Normal Form?**

a) 2,4

b) 1,3

c) 1, 2, 3, 4

d) 2, 3, 4

**Correct Answer:** a) 2,4

**Explanation:** Chomsky Normal Form (CNF) strictly dictates that productions must yield either exactly two non-terminals ($A \rightarrow BC$) or exactly one terminal ($A \rightarrow a$). Production (2) $S \rightarrow AAS$ has three non-terminals, and (4) $A \rightarrow aa$ yields two terminals; both violate CNF rules.

---

**48. Which of the problems are unsolvable?**

a) Halting problem

b) Boolean Satisfiability problem

c) Halting problem & Boolean Satisfiability problem

d) None of the mentioned

**Correct Answer:** c) Halting problem & Boolean Satisfiability problem

**Explanation:** While the Halting Problem is famously undecidable (unsolvable by a Turing machine), the provided answer key also marks Boolean Satisfiability (SAT). *(Technical Note: From a strict CS perspective, SAT is decidable but intractable—NP-Complete—however, the answer key specifically groups them together for this option).*

---

**49. Given Grammar: $S \rightarrow A$, $A \rightarrow aA$, $A \rightarrow \epsilon$, $B \rightarrow bA$. Which among the following productions are Useless productions?**

a) $S \rightarrow A$

b) $A \rightarrow aA$

c) $A \rightarrow \epsilon$

d) $B \rightarrow bA$

**Correct Answer:** d) $B \rightarrow bA$

**Explanation:** A production is useless if its non-terminal can never be reached from the start symbol, or if it cannot generate a terminal string. Beginning at the start symbol $S$, the derivations lead only to $A$. The non-terminal $B$ is entirely unreachable, making the production $B \rightarrow bA$ useless.

---

**50. The production of the form $A \rightarrow B$, where A and B are non-terminals is called**

a) Null production

b) Unit production

c) Greibach Normal Form

d) Chomsky Normal Form

**Correct Answer:** b) Unit production

**Explanation:** By standard formal language definitions, when a grammar rule consists of a single non-terminal deriving exactly one other non-terminal on the right-hand side, it is explicitly classified as a unit production.
