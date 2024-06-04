

Assignment

1. Get used to the functions `TridiagonalToeplitz`, documented here https://docs.quantum.ibm.com/api/qiskit/0.40/qiskit.algorithms.linear_solvers.TridiagonalToeplitz, with the following syntax

`class TridiagonalToeplitz(num_state_qubits, main_diag, off_diag, tolerance=0.01, evolution_time=1.0, trotter_steps=1, name='tridi')`

* Set `num_state_qubits` to be the qubit number $n$. In this case, the fucntion will output $2^n \times 2^n$ matrix.

* Perform simulations for qubit numbers $n=1,2,.., 5$. 

Use the Qiskit HHL class documented in the Jupyter notebook ``hhl_tutorial.ipynb  to:

* Provide explicit quantum circuits that prepare a quantum solution of the linear system. To this end, you can use the `state` property of the `LinearSolverResult` object returned by `HHL.solve()`.

* Use the HHL quantum algorithm to estimate  the following properties for the computed solutions: 
** The vector norm $\|x\|^2$ (use the `euclidean_norm' property).
** The average of the vector entries.
** The inner product $\langle x B x \rangle$ where $$

 the norm of the solution $\|\mathbf{x}\|$ of a solution vector.

* Consider the following particular cases:

    * $a,b$ are randomly chosen real numbers in the interval $[-1,1]$.
    * $a,b$ are randomly chosen $\log(n)$-digit numbers in the interval $[-n,n]$.
    * $a,b$ are randomly chosen $n$-digit numbers in $[-2^n, 2^n]$.

    `LinearSolverResult`   

* Use the classical Numpy solver `linalg` to verify your solutions.

* Compare the complexity of the exact HHL method vs the approximate HHL method. To this end, compare the naive default implementation of HHL vs the efficient implementation of the Qiskit library, which implements the Hamiltonian simulation algorihtm for tridiagonal matrices. For sizes up to n=4.

* Estimate the complexity for larger qubits sizes only for the approximate efficient method.

* Choosing different observables, use the quantum algorithm