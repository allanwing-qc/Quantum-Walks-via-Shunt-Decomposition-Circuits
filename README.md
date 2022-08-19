# Quantum-Walks-via-Shunt-Decomposition-Circuits

A coined quantum walk (CQW) considers a walker that moves between the vertices of a graph $\mathcal{G}(V,E)$ with adjacency matrix $\mathcal{A}$, where $V$ and $E$ are the vertex and edge sets, respectively. A CQW is defined by three elements: the quantum state of a walker, the evolution operator of the system and a set of measurement operators. The state of walker at time $t$ is represented by a composite quantum state 

$|\psi(t) \rangle = \sum\limits_{i,j} a_{ij}|c_i \rangle \otimes |v_j\rangle$,

where $|v_j\rangle \in \mathcal{H}_P$ is a quantum state associated to vertex $v_j$, and $|c_k\rangle \in \mathcal{H}_C$ is a quantum state associated to a set of edges $\{v_j,v_i\} \in E$. $\mathcal{H}_P$ and $\mathcal{H}_C$ are Hilbert spaces of size $n$ and $m$, and are called position and coin spaces, respectively. The evolution operator $U$ is conformed by the product of the shift and coin operators, i.e.

$U=S(C\otimes I_{n})$

One step of the walker consists in the application of $U$ to $|\psi(t)\rangle$, the walker standing on vertex $v_j \in V$ first gets in a superposition of states by the action of $C\otimes I_{n'}$, and then moves toward all the adjacent vertices at the same time, by the action of $S$. The state of the system after $t$ steps is given by $|\psi(t)\rangle = U^t |\psi_0 \rangle$, where $|\psi_0 \rangle$ is the initial state of the walker. 

Finally, we define the measurement operator of the system as 

$M_j = I_{m'} \otimes |v_j\rangle \langle v_j|$

and the probability to find a walker on vertex $v_j$ after $t$ steps is given by

$P(|v_j\rangle) = \langle \psi(t)|M_j^{\dagger}M_j|\psi(t) \rangle$


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/5-cycle_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/3-cube_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/7-line_github.png?raw=true)


![github-small](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/k4_github.png?raw=true )
