----------------------------------
***An anonymized submission containing the code to the submission titled: "On the Parallel I/O Optimality of Linear Algebra Kernels: Near-Optimal Matrix Factorizations".***
----------------------------------
IT CONTAINS:

-the code containing LU and Cholesky factorizations used in the paper, together with the launch scripts,

-authorsKit's script output (AuthorsKitOutput.txt),

-appendix containing proofs of Lemmas 2-7 included in the paper (proof_appendix.pdf).


## CODE 

Inside the "code" folder, there is a README.md file containing detailed instructions on the setup. The experiments were run on Piz Daint supercomputer.

## Estimated time needed for the measurements
In general, it is difficult to give a time estimate since the node allocation mechanisms of Piz Daint are intransparent. However, the experiment that will run the longest (excluding queueing time) is `launch_weak_conflux_256` which we estimate to take roughly 3.5 hours.

We ran the experiments on the CPU partition of Piz Daint supercomputer, which hosts two Intel E5-2695 processors v4 per node, yielding 2.4 GLOPs/s per node.

**A rough estimate of a single-run time for a given matrix size N and number of nodes P, assuming the achieved performance of 50% of hardware peak:**   
1. FLOPs per node required: LU - N^3/(3 * P), Cholesky - N^3/(6 * P).
2. Node performace: B = 2.4 * 10^9 FLOPs/s * 50% (efficiency)
3. time: T_LU = FLOPs/B = N^3 / (3.6 P) us,  T_Chol = N^3 / (7.2 P) us

Note that in the paper, for each combination of N and P, we tested four libraries, four block sizes, and five runs for statistics.



