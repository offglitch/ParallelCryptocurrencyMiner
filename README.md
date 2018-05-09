# Project 3: Parallel Cryptocurrency Miner

See instructions here: https://www.cs.usfca.edu/~mmalensek/cs220/assignments/project-3.html

## Written Responses

Edit this readme.md file to answer the following questions:

### Busy-waiting vs. Condition Variables

Once you have condition variables working in your program, compare the performance of busy waiting with condition variables. To ensure a fair comparison, use a single thread.

Report for the original program as well as modified version:

1. Total program run time
2. Hashes per second
3. CPU usage during execution (use the `top` command to get a rough estimate of the average CPU usage)

Original: 
Number of threads: 1
............
Solution found by thread 0:
Nonce: 12308441
Hash: 000000FCAFFDDD17CD5CC78D8698918AF0F80055
12308440 hashes in 26.95s (456672.15 hashes/sec)


Modified: 
Number of threads: 1
.
Solution found by thread 1:
Nonce: 1011686
Hash: 000000B976A3E2B94CB9AB668E0C9C727782787B
1011700 hashes in 1.51s (669267.38 hashes/sec)

Which version performs better? Is this the result you expected? Why or why not?

Modified version performs better, and this is the result i expected. 

### Nonces Per Task

Experiment with different values for `NONCES_PER_TASK`. What value yields the best performance in terms of hashes per second on your machine?

100 

### Performance I

When evaluating parallel programs, we use speedup and efficiency. Why are these metrics not as useful when measuring the performance of our parallel crytocurrency miner?

amdahls law

### Performance II

Using any of the `kudlick` machines (in our 220 classroom), what is the highest performance you were able to achieve in terms of hashes per second? What configuration did you use (`NONCES_PER_TASK`, number of threads, block data, compiler options)?



