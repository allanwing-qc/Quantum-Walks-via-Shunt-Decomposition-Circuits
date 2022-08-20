# Quantum-Walks-via-Shunt-Decomposition-Circuits

A discrete-time coined quantum walk (DTCQW) considers a walker that moves between the vertices of a graph $\mathcal{G}(V,E)$ with adjacency matrix $\mathcal{A}$, where $V$ and $E$ are the vertex and edge sets, respectively. A CQW is defined by three elements: the quantum state of a walker, the evolution operator of the system and a set of measurement operators. The state of walker at time $t$ is represented by a composite quantum state 

$|\psi(t) \rangle = \sum\limits_{i,j} a_{ij}|c_i \rangle \otimes |v_j\rangle$,

where $|v_j\rangle \in \mathcal{H}_P$ is a state associated to vertex $v_j \in \mathbb{Z}$, and $|c_k\rangle \in \mathcal{H}_C$, with $c_k \in \mathbb{Z}$, is a state associated to a set of edges $\{v_j,v_i\} \in E$. For simplicity consider $|v_j\rangle$ and $|c_k\rangle$ be associated to canonical vectors. $\mathcal{H}_P$ and $\mathcal{H}_C$ are Hilbert spaces of size $n'$ and $m'$, and are called position and coin spaces, respectively. The evolution operator $U$ is conformed by the product of the shift and coin operators, i.e.

$U=S(C\otimes I_{n})$.

One step of the walker consists in the application of $U$ to $|\psi(t)\rangle$, the walker standing on vertex $v_j \in V$ first gets in a superposition of states by the action of $C\otimes I_{n}$, and then moves toward all the adjacent vertices at the same time, by the action of $S$. The state of the system after $t$ steps is given by $|\psi(t)\rangle = U^t |\psi_0 \rangle$, where $|\psi_0 \rangle$ is the initial state of the walker. 

Finally, we define the measurement operator of the system as 

$M_j = I_{m} \otimes |v_j\rangle \langle v_j|$,

and the probability to find a walker on vertex $v_j$ after $t$ steps is given by

$P(|v_j\rangle) = \langle \psi(t)|M_j^{\dagger}M_j|\psi(t) \rangle$.

Different methods to construct evolution operators to perform walks on different topologies have been proposed. Particularly, the case in which the shift operator of a quantum walk is a block diagonal matrix, whose block elements are permutation matrices that allows us to easily manipulate $S$.

To construction of the evolution operator, let $\mathcal{G}$ be $m$-regular graph, with adjacency matrix $\mathcal{A}(\mathcal{G})$. Suppose $\mathcal{A}$ can be decomposed as the sum of $m$ permutation matrices, $\mathcal{P}_i \in \mathbb{R}^{n \times n}$, i.e.

$\mathcal{A} = \sum\limits_{i=0}^{m-1} \mathcal{P}_i$.

We call each permutation matrix a $shunt$. Next, we associate each shunt with a coin basis state, and define the shift operator of the system as 

$S= \sum\limits_{i=0}^{m-1} |c_i\rangle \langle c_i| \otimes \mathcal{P}_i$,

Because $S$ is a block diagonal matrix with unitary matrices as entries, $S$ is unitary too, and contains the same information of the connections between nodes than the original adjacency matrix.


Let $\mathcal{G}(V,E)$ be a graph with connected components of order $n'=2^n$, whose adjacency matrix can be decomposed into the sum of $m'=2^m$ permutation matrices and whose vertices and edges are both labeled by integers. Associated to the vertices of the graph $\mathcal{G}$, there exists a set of $2^n$ basis vectors $\{|v_j \rangle: v_j \in \mathbb{Z}\}$ that span $H_P$, and associated to the edges connected to vertex $v_i$ a set of $2^m$ basis vectors $\{|c_i \rangle: c_i \in \mathbb{Z}\}$ that span $H_C$.

Now consider $f_V: \mathbb{Z} \rightarrow B$, where $B$ is the set of all bitstrings. In order to map the basis states of the Hilbert spaces $H_c$ and $H_p$ into a bitstring, we must consider the basis states of a qubit:


In order to map the basis states of $H_c$ and $H_p$ into a composite state of qubits, we must map $v_j$ and $c_k$ into bitstring notation. Thus, we define the function $f_V: \mathbb{Z} \rightarrow B$, where $B$ is the set of all bitstrings, and consider the basis states of a qubit to be given by

$|0\rangle = <1,0>$, $|1\rangle = <0,1>$

In this way, we are able to do the following map

$|f_V(v_i) \rangle = |q_0q_1\dots q_n\rangle = |q_0 \rangle \otimes |q_1 \rangle \otimes \dots \otimes |q_n\rangle$,

where $q_i \in \{0,1\}$.

This means that every basis vector $|v_i\rangle$ can be rewritten as a composite state given by the tensor product of $n$ qubits. The same mapping is done for the coin space, allowing us to express the state vector of a quantum walker, $|\psi \rangle = |c_i\rangle \otimes |v_i \rangle$, in bitstring notation. 

This mapping can be represented in an $n+m$-qubit quantum circuit, where the first $n$ qubits form a register $|q_0 q_1 \dots q_{n-1} \rangle$ that correspond to the position states, and the last $m$ qubits form a register $|q_{n} q_{n+1} \dots q_{n+m-1} \rangle$ that correspond to the coin states.

To completely map a quantum walk into a quantum circuit, we need to express the evolution operator, $U=S(C \otimes I_P)$, as a set of quantum gates. A general method can be followed for graphs whose adjacency matrices can be decomposed in $2^m$ permutation matrices $\mathcal{P}_i$ of size $2^n$, which will be used as block diagonal elements of $S$.


Given that all matrices $\mathcal{P}_i$ are unitary, there exists a quantum gate representation for all of them. Out of the quantum gate $\mathcal{P}_i$, we can create a controlled gate, $C^{m}_j(\mathcal{P}_i)$, which uses all the qubits of the coin register as control qubits, as shown in the Fig. 1(a).


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/block_diagonal_to_circuit_github.png?raw=true)


We call the black and the white dots in this figure $controls$. The pattern that they create can be interpreted as binary code, where the black controls represent a 1, the white controls represent a 0 and the less significant bit of the bitstring is the upper-most control in the position register. The subindex $j = 0,1, \dots, 2^m-1$ in $C^{m}_j(\mathcal{P}_i)$ represents the value of the bitstring formed by the control qubits of the gate. 


The result of controlling $\mathcal{P}i$ is a $2^{n+m}$ block diagonal matrix, where all the diagonal elements of the matrix are the $2^n \times 2^n$ identity, $I_{2^n}$, except for the $j$th element, which will be the matrix $\mathcal{P}_i$. This is given by the equation

$C^{m}j(\mathcal{P}i) = I_{2^{in}} \oplus \mathcal{P}{i}\oplus I_{2^{(2^m-i-1)n}}$,

where $i,j = 0,1, \dots, 2^{m}-1$. Notice that $i$ and $j$ do not have to coincide, although every index $j$ must be related to only one fixed index $i$, which just means that the matrices $\mathcal{P}_i$ can be shuffled in the diagonal indistinguishably. Thus we define $i$ as a function of $j$.

This way, we can find $2^m$ block diagonal gates $C^m_j(\mathcal{P}{i(j)})$ in which the matrices $\mathcal{P}{i(j)}$ are placed in a different position $j$ relative to each other, and the rest of the elements are $I_{2^n}$. When these controlled gates are placed next to each other in a quantum circuit, as in Fig. 2(b), the associated matrix representation is given by

$S = \prod\limits_{j=0}^{2^m-1} C_j^m(\mathcal{P}{i(j)})$,

a block diagonal operator whose elements are the additive decomposition of the adjacency matrix associated to graph $\mathcal{G}$, i.e. we obtain $S= \sum\limits_{i=0}^{m-1} |c_i\rangle \langle c_i| \otimes \mathcal{P}_i$. 

To complete the mapping of the evolution operator we can add a Hadamard or a Grover coin to the qubits of the coin register.

Based on this method, we present the circuit form of the evolution operators to perform quantum walks on the 5-cycle, 7-line, the 3-cube with self-loops, the 4-vertex complete graph with self-loops, as shown in Figures 2,3,4 and 5.


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/5-cycle_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/3-cube_github.png?raw=true)


![alt text](https://github.com/allanwing-qc/Quantum-Walks-via-Shunt-Decomposition-Circuits/blob/main/7-line_github.png?raw=true)


