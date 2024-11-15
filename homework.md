

# Assignment HHL

In this exercise we will create a GitHub repository for your project. Clone it into your personal computer and install the required packages to run the quantum lineary systems algorithm tutorial file. Run the Jupyter notebook "hhl_tutorial.ipnb". Make sure it runs without errors. Complete the exercises below in the Jupyter tutorial and submit your GitHub repository back to the instructor at jbermejovega at go ugr dot es.


1. Set `num_state_qubits` to be the qubit number $n$. In this case, the fucntion will output $2^n \times 2^n$ matrix. Perform simulations for qubit numbers $n\leq 5$. Answer: what is the maximum number of qubits $M$ that you can simulate in your machine? State the model of the processor that you have in your PC and, if available, the graphics card or GPU.

2. Use the Qiskit HHL class documented in the Jupyter notebook ''hhl_tutorial.ipynb''  to provide explicit quantum circuits that prepare a quantum solution of the linear system. To this end, you can use the `state` property of the `LinearSolverResult` object returned by `HHL.solve()` in the Jupyter notebook and the `print` command. 

3. Use the HHL quantum algorithm to estimate properties for the HHL solutions to different systems of equations. To this end, choose a system $Ax=b$ defined by a triadiagonal matrix $A$ that you can solve using HHL with at most $M\leq 5$ qubits. Generate with the `TridiagonalToeplitz` class `class TridiagonalToeplitz(num_state_qubits, main_diag, off_diag, tolerance=0.01, evolution_time=1.0, trotter_steps=1, name='tridi')` (documentation: https://docs.quantum.ibm.com/api/qiskit/0.40/qiskit.algorithms.linear_solvers.TridiagonalToeplitz). Solve the system for your chosen matrix and report the following properties for the solutions: 
(a) The vector norm $\|\mathbf{x}\|$ of a solution vector (use the `euclidean_norm` property). (b) The average of the vector entries. (c) The inner product $\langle x B x \rangle$ where $B$ is a Hermitian observable of your choice. (d) Verify your solutions using the classical Numpy solver `linalg`, `LinearSolverResult` to verify your solutions.

4. Study the influence of the performance with the size of the matrix entries for Triagonal matrices. Use different ranges for the matrix entries: (a) $a,b$ are randomly chosen real numbers in the interval $[-1,1]$. (b) $a,b$ are randomly chosen $\log(n)$-digit numbers in the interval $[-n,n]$. (c) $a,b$ are randomly chosen $n$-digit numbers in $[-2^n, 2^n]$. What is the influence of the size of the range in the cost of running HHL?

Tips:
* You may use the classical Numpy solver `linalg`, `LinearSolverResult` to verify your solutions.
* Be careful with the complexity of the exact HHL method vs the approximate HHL method. The naive default implementation of HHL the efficient implementation of the Qiskit library commits no errorr but can take more time to run. You can use the TridiagonalToeplitz function, which implements the Hamiltonian simulation algorihtm for larger tridiagonal matrices. Estimate the complexity for larger qubits sizes only for the approximate efficient method.