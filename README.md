---
Quantum Machine Learning
=============
---
In quantum information theory, a mixed state of the composite system is described by a density matrix acting on the composite Hilbert space (i.e the tensor product of the sub-sytems Hilbert spaces)[1].
In these composite systems, a physical phenomenon can occur, called entanglement, such that the quantum state of each subsystem cannot be described independent of the state of the other subsystems, and measurement of physical properties performed on entangled subsystems are found to be correlated. Not all the composite systems have this property; a state without quantum entanglement is called a separable quantum state[2].

Given a density matrix for a composite system, the task to find whether or not the state is entangled in general, is considered to be a difficult task, although in some special cases there exists a simple analytic method[3]. This problem is sometimes called the separability problem in quantum information theory and it's been shown to be NP-hard[4]. A separability criterion or an entanglement witness, is a necessary condition a density matrix must satisfy to be separable or entangled, respectively. But it's only a necessary condition (and not sufficient) so that if the criterion or witness does not hold, the test is inconclusive.

In cases which the Hilbert space dimension is (2,2) and (2,3), the Peres-Horodecki criterion (also known as PPT criterion) is a necessary and sufficient condition for separability[3]. In higher dimensions, the test is inconclusive. The criterion states that in bipartite states, if a state is separable, its partial transpose has non-negative eigenvalues. In other words, if the partial transpose has a negative eigen value, the state is guaranteed to be entangled. The result is independent of the party that was transposed.

In two qubit state, 15 features from tensor product of pauli matrices and identity operator, can fully describe a density matrix (neglecting the trivial 1 resulted from the identity operators)[2]. The very first step of our project starts with the task that given these 15 features, machine should learn to identify whether a density matrix is separable or not. It is expected that machine achieves a 1.0 score with a supervised learning for this case, since the PPT criterion can be actually found from the determinant of the partially transposed matrix, which is in turn a 4th degree polynomial of these 15 features. So a linear regression with a 4th degree polynomial feature should work.

In the next step, we will find the feature importance to find out the possibility of deciding entanglement with fewer features with a good degree of certainty. Moreover, we check if it is possible to decide with a higher certainty, with fewer features using measurements other than the pauli matrices, such as non-orthogonal measurements.

Another possibility which will be analyzed is that given a number of witnesses and a density matrix, is it possible for the machine to predict the witness which works better for the case, using machine learning algorithms.

In addition, robustness of each method will be analyzed to provide a robust method with higher noise resistance for deciding the separability.

Finally, we can employ these machine learning methods to higher dimensions to see whether it is possible to find a less complex separability criterion or entanglement witness with a high certainty.

-----
[1] Isaac Chuang and Michael Nielsen, Quantum Computation and Quantum Information, second ed. , 2010

[2] Wikipedia

[3] M. Horodecki, P. Horodecki, R. Horodecki, Separability of mixed states: necessary and sufficient conditions, Phys. Lett. A 223, 1 ,1996.

[4] Sevag Gharibian, Strong NP-Hardness of the Quantum Separability Problem, Quantum Information and Computation, Vol. 10, No. 3&4, pp. 343-360, 2010. arXiv:0810.4507.
