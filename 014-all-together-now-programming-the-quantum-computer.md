# All Together Now! Programming the Quantum Computer

Jennifer Fernick

Thing to take away: the various levels of abstraction on a quantum computer

Quantum computing: using quantum phenomena to preform computational tasks. Offers exponential speedups over classical algorithms for some applications.

Downsides:
* Sensitive to environmental noise
* Measurement of quantum states destroys superposition -- how can we create RAM in quantum system?
* No cloning theorem

Quantum mechanics: probability theory but over the complex numbers

qubits: a superposition of values 0 and 1

When measured, superposition collapses into a discrete state

qubits can be made of many things:
* Particle spins
* Polarizations of photons

N qubits = 2^N complex coefficients, so a 64-qubit computer can represent 18 quintillion parallel operations

Stages of quantum computers:
* Single qubit operations
* Multiple qubit operatins
* Error correction
* Memory of qubits after the fact

Quantum gates:
* Configuration of qubits to perform logical operations
* Quantum circuits are composed of reversable quantum gates so that we can do basic operations on an n-qubit register

Quantum programming language research involves:
* High level formalisms for reasoning about quantum algorithms
* Compiler design -- what are primitive operations? What level of abstractions should be offered?
* Highly difficult due to variety of quantum computer implementation approaches. Basic primitves are unclear.
* Probably have programming model similar to Google Cloud Compute: a remote procedure call over a highly specialized API

Applications:
* Simulations
* Metrology
* Optimization
* Materials science
* Chemistry
* Machine learning - Grover's algorithm

But that isn't the sexy stuff. The sexy stuff is Shore's algorthm: a proposed quantum algorithm that would dramatically speed up the factoring of large numbers into component primes, thus breaking public key cryptography and therefore the Internet.

Quantum Computational complexity
* Does not break the Church-Turing thesis; a classical computer can do everything a quantum computer can do, just slower
* There are probably algorithms that are slow for a classical computer (in NP) but not for a quantum computer
