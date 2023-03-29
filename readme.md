# The HHL Quantum Algorithm Applied to Data Fitting

The HHL (Harrow-Hassidim-Lloyd) algorithm is a quantum algorithm that can solve linear systems of equations exponentially faster than classical algorithms. This repository has a sandbox for exploring the HHL algorithm as well an application of the HHL algorithm to a data-fitting problem. 

## Description of Files.

- `hhl-sandbox.ipynb` - A jupyter notebook interactive sandbox for testing out different inputs to the HHL algorithm. This file also contains a step by step Qiskit implementation of the algorithm.
- `data-fitting.ipynb` - A jupyter notebook step-by-step application of HHL to solve a data-fitting problem.
- `final-writeup.pdf` - A writeup describing in much greater detail the theory behind the HHL algorithm.
- `HHL-Algo-Paper.pdf` - The paper pioneering the HHL algorithm.

## HHL Algorithm Description. 
Given a matrix A and a vector b, the HHL algorithm solves the linear system of equations $Ax = b$ to find the vector $x$. 

![HHL Algo](https://qiskit.org/textbook/ch-applications/images/hhlcircuit.png)

The HHL algorithm can be summarized into three main steps:
- Quantum phase estimation: This step involves preparing a superposition of eigenstates of matrix A, which is achieved using quantum phase estimation. This step requires a quantum register for storing the eigenvalues of A and an ancilla qubit for carrying out the quantum phase estimation.
- Conditioned rotation: In this step, a controlled rotation is applied to the ancilla qubit based on the eigenvalues obtained in the previous step. This step requires additional quantum gates and registers for storing the eigenvectors of A.
- Measurement and post-processing: In this final step, the ancilla qubit is measured to obtain an estimate of the solution vector x. The measurement outcome is then post-processed using classical computation to obtain the final solution.

The HHL algorithm has several advantages over classical algorithms, including its ability to solve certain types of linear systems of equations exponentially faster than classical algorithms. See the `final-writeup.pdf` writeup for the specifics of the HHL Algorithm.