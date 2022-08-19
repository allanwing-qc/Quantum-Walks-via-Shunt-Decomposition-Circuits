# Quantum-Walks-via-Shunt-Decomposition-Circuits

A coined quantum walk considers a walker that moves between the vertices of a graph $\mathcal{G}(V,E)$ with adjacency matrix $\mathcal{A}$, where $V$ and $E$ are the vertex and edge sets, respectively. A CQW is defined by three elements: the quantum state of a walker, the evolution operator of the system and a set of measurement operators. The state of walker at time $t$ is represented by a composite quantum state 

\begin{equation}
\label{quantum_state_walker}
|\psi(t) \rangle = \sum\limits_{i,j} a_{ij}|c_i \rangle \otimes |v_j\rangle, 
\end{equation}
where $|v_j\rangle \in \mathcal{H}_P$ is a quantum state associated to vertex $v_j$, and $|c_k\rangle \in \mathcal{H}_C$ is a quantum state associated to a set of edges $\{v_j,v_i\} \in E$. $\mathcal{H}_P$ and $\mathcal{H}_C$ are Hilbert spaces of size $n$ and $m$, and are called position and coin spaces, respectively. The evolution operator $U$ is conformed by the product of the shift and coin operators, i.e.

\begin{equation}
    U=S(C\otimes I_{n'})
\end{equation}


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/5-cycle_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/3-cube_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/7-line_github.png?raw=true)


![github-small](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/k4_github.png?raw=true )
