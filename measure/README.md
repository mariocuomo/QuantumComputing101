# Measure and Collapse of the Wavefunction

The first experiments with qubits focused on understanding how to measure their quantum states. Measurement in quantum mechanics is a unique process because it causes the qubit to collapse from a superposition of states into one of the basis states.

$$
|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle
$$

In [intro](https://github.com/mariocuomo/QuantumComputing101/edit/main/intro/README.md) to Quantum Computing, we described that a **balanced superposition** for a single qubit is a quantum state where the qubit has equal probabilities of being measured in either of its basis states.

Let's experiment with _IBM Quantum Learning_.

<div align="center">
  <img src="https://github.com/mariocuomo/QuantumComputing101/blob/main/img/balancedsuperposition-measure.png">
</div>

This quantum circuit involves one qubit and one classical bit. Here’s a step-by-step description:

1. **Hadamard Gate (H)** <br>
The circuit starts by applying a [Hadamard gate](https://github.com/mariocuomo/QuantumComputing101/tree/main/operators/Hadamard) to the qubit (q[0]). This gate creates a superposition state from the initial state <mi>|0</mi><mo stretchy="false">⟩</mo>. After the Hadamard gate, the qubit is in the state:

$$
|\psi\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)
$$

2. **Measurement in Z Basis** <br>
Finally, there is a measurement gate in the Z basis, which measures the qubit in the standard computational basis <mi>|0</mi><mo stretchy="false">⟩</mo> and <mi>|1</mi><mo stretchy="false">⟩</mo>. The result of this measurement is also stored in the classical bit (c4)

