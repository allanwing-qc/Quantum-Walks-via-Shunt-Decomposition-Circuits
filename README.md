# Quantum-Walks-via-Shunt-Decomposition-Circuits

A discrete-time coined quantum walk (DTCQW) considers a walker that moves between the vertices of a graph $\mathcal{G}(V,E)$ with adjacency matrix $\mathcal{A}$, where $V$ and $E$ are the vertex and edge sets, respectively. A CQW is defined by three elements: the quantum state of a walker, the evolution operator of the system and a set of measurement operators. The state of walker at time $t$ is represented by a composite quantum state 

$|\psi(t) \rangle = \sum\limits_{i,j} a_{ij}|c_i \rangle \otimes |v_j\rangle$,

where $|v_j\rangle \in \mathcal{H}_P$ is a quantum state associated to vertex $v_j$, and $|c_k\rangle \in \mathcal{H}_C$ is a quantum state associated to a set of edges $\{v_j,v_i\} \in E$. $\mathcal{H}_P$ and $\mathcal{H}_C$ are Hilbert spaces of size $n$ and $m$, and are called position and coin spaces, respectively. The evolution operator $U$ is conformed by the product of the shift and coin operators, i.e.

$U=S(C\otimes I_{n})$.

One step of the walker consists in the application of $U$ to $|\psi(t)\rangle$, the walker standing on vertex $v_j \in V$ first gets in a superposition of states by the action of $C\otimes I_{n'}$, and then moves toward all the adjacent vertices at the same time, by the action of $S$. The state of the system after $t$ steps is given by $|\psi(t)\rangle = U^t |\psi_0 \rangle$, where $|\psi_0 \rangle$ is the initial state of the walker. 

Finally, we define the measurement operator of the system as 

$M_j = I_{m} \otimes |v_j\rangle \langle v_j|$,

and the probability to find a walker on vertex $v_j$ after $t$ steps is given by

$P(|v_j\rangle) = \langle \psi(t)|M_j^{\dagger}M_j|\psi(t) \rangle$.

Different methods to construct evolution operators to perform walks on different topologies have been proposed. Particularly, the case in which the shift operator of a quantum walk is a block diagonal matrix, whose block elements are permutation matrices that allows us to easily manipulate $S$.

To construction of the evolution operator, let $\mathcal{G}$ be $m$-regular graph, with adjacency matrix $\mathcal{A}(\mathcal{G})$. Suppose $\mathcal{A}$ can be decomposed as the sum of $m$ permutation matrices, $\mathcal{P}_i \in \mathbb{R}^{n \times n}$, i.e.

$\mathcal{A} = \mathcal{P}_0 + \mathcal{P}_1 + \dots + \mathcal{P}_{m}$.

We call each permutation matrix a $shunt$. Next, we associate each shunt with a coin basis state, and define the shift operator of the system as expressed in eq. (\ref{shift_per_diag}). 

$S= \sum\limits_{i=0}^{m-1} |c_i\rangle \langle c_i| \otimes \mathcal{P}_i$,

Because $S$ is a block diagonal matrix with unitary matrices as entries, $S$ is unitary too, and contains the same information of the connections between nodes than the original adjacency matrix.  



![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/5-cycle_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/3-cube_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/7-line_github.png?raw=true)


![github-small](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/k4_github.png?raw=true )
