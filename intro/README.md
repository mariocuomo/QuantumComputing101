# Quantum Computing introduction

**Quantum computing** is an advanced field of computer science that leverages the principles of quantum mechanics to perform computations that are beyond the capabilities of classical computers.

Quantum computing differs from classical computing in several fundamental ways:

1. **Basic Units of Information**
    - **Classical Computing**: Uses bits as the basic unit of information, which can be either 0 or 1.
    - **Quantum Computing**: Uses qubits, which can be 0, 1, or both simultaneously due to the principle of superposition1.
    
2. **Superposition**
    - **Classical Computing**: Bits exist in a definite state (either 0 or 1).
    - **Quantum Computing**: Qubits can exist in multiple states at once, allowing quantum computers to process a vast amount of information simultaneously.
    
3. **Entanglement**
    - **Classical Computing**: Bits operate independently.
    - **Quantum Computing**: Qubits can become entangled, meaning the state of one qubit is directly related to the state of another, no matter the distance between them. This property can be used to perform complex computations more efficiently.

4. **Interference**
     - **Classical Computing**: Does not utilize interference.
     - **Quantum Computing**: Uses quantum interference to amplify correct answers and cancel out incorrect ones, improving the probability of arriving at the correct solution.

5. **Processing Power**
     - **Classical Computing**: Processes information in a linear, step-by-step manner.
     - **Quantum Computing**: Can solve certain problems much faster by exploring many possible solutions simultaneously, making it particularly powerful for tasks like cryptography, optimization, and simulating molecular structures.


But... physically, what are qubits? <br>
Physically, qubits can be created using various quantum systems. Here are some common methods:

- **Superconducting Circuits** <br>
These use superconducting materials to create qubits. Superconducting qubits are made by cooling certain materials to very low temperatures, allowing them to exhibit quantum properties. These circuits can be manipulated using microwave pulses.

- **Trapped Ions** <br>
Individual ions (charged atoms) are trapped and manipulated using electromagnetic fields. The energy levels of these ions can represent qubit states. Lasers are used to control and read out the states of these ions.

- **Photons** <br>
Photons, or particles of light, can be used as qubits. The polarization state of a photon (the direction in which it oscillates) can represent different qubit states. Photons are manipulated using optical devices like beam splitters and wave plates.

- **Spin Qubits** <br>
The spin of electrons or nuclei can be used to create qubits. The spin state (up or down) represents the qubit states. These qubits are manipulated using magnetic fields and microwave radiation.

- **Quantum Dots** <br>
These are tiny semiconductor particles that can trap electrons. The quantum state of the trapped electron can be used as a qubit. Quantum dots are controlled using electrical gates.
Each of these methods has its own advantages and challenges, and researchers are exploring all of them to find the most effective way to build scalable quantum computers.


---
> [!IMPORTANT]
> In our exploration of Quantum Computing, **we will concentrate solely on the mathematical models created using qubits**, rather than delving into their physical implementation. This approach allows us to abstract away the complexities of hardware and focus on the theoretical underpinnings and computational advantages that qubits offer. By leveraging the principles of _superposition_, _entanglement_, and _interference_, we can develop and analyze quantum algorithms that solve problems more efficiently than classical methods. This theoretical focus will enable us to better understand the potential of quantum computing and its applications, without being constrained by the current technological limitations of qubit fabrication and manipulation.

---

## Qubit
A **qubit**, or **quantum bit**, is the fundamental unit of information in quantum computing. Unlike a classical bit, which can be either 0 or 1, a qubit can exist in a **superposition of both states simultaneously**. This means that a qubit can represent both 0 and 1 at the same time, thanks to the principles of quantum mechanics.

A qubit can be mathematically represented as a **linear combination of its basis states**, typically denoted as **<mi>|0</mi><mo stretchy="false">⟩</mo>** and **<mi>|1</mi><mo stretchy="false">⟩</mo>**. The general state of a qubit can be written as:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
$$


<mi>α</mi> and <mi>β</mi> are **complex numbers** that represent the probability amplitudes of the qubit being in the <mi>|0</mi><mo stretchy="false">⟩</mo> and <mi>|1</mi><mo stretchy="false">⟩</mo> states, respectively. These amplitudes must satisfy the **normalization condition**:

$$
|\alpha|^2 + |\beta|^2 = 1
$$

Qubit can be visualized using the **Bloch Sphere**. <br>
The Bloch sphere is a visual representation of the state of a **single qubit**. Imagine a sphere where any point on its surface represents a possible state of the qubit. Here’s a simple breakdown:

- **Poles** <br>
The north pole represents the state <mi>|0</mi><mo stretchy="false">⟩</mo> and the south pole represents the state <mi>|1</mi><mo stretchy="false">⟩</mo>.

- **Superposition** <br>
Any point on the surface of the sphere represents a superposition of <mi>|0</mi><mo stretchy="false">⟩</mo> and <mi>|1</mi><mo stretchy="false">⟩</mo>. The position on the sphere is determined by two angles, <mi>θ</mi> and <mi>φ</mi>, which describe the state of the qubit.

<div align="center">
    <img src="https://github.com/mariocuomo/QuantumComputing101/blob/main/img/Bloch_sphere.png" width="200">
</div>


A qubit can be represented as a **vector** in a two-dimensional complex vector space.

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \begin{pmatrix}
\alpha \\
\beta \\
\end{pmatrix} = \alpha \begin{pmatrix}
1 \\
0 \\
\end{pmatrix} + \beta \begin{pmatrix}
0 \\
1 \\
\end{pmatrix}
$$

---

## Measure and Collapse of the Wavefunction
Before measurement, a qubit can be in a superposition of <mi>|0</mi><mo stretchy="false">⟩</mo> and <mi>|1</mi><mo stretchy="false">⟩</mo>. Upon measurement, the qubit collapses to either  <mi>|0</mi><mo stretchy="false">⟩</mo> or <mi>|1</mi><mo stretchy="false">⟩</mo> with different probabilities that depend on <mi>α</mi> and </mi><mi>β</mi>
</annotation></semantics></math> respectively.

### Example 1

$$
|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle
$$

After measurements, the probability to collapse to <mi>|0</mi><mo stretchy="false">⟩</mo> is equal to the probability to collapse to <mi>|1</mi><mo stretchy="false">⟩</mo>, that is

$$
\left|\frac{1}{\sqrt{2}}\right|^2 = \frac{1}{2}
$$


### Example 2

$$
|\psi\rangle = \frac{1}{3}|0\rangle + \frac{2 \sqrt{2}}{3}|1\rangle
$$

After measurements, the probability to collapse to <mi>|0</mi><mo stretchy="false">⟩</mo> is 

$$
\left|\frac{1}{3}\right|^2 = \frac{1}\{9}=11.1 %
$$

After measurements, the probability to collapse to <mi>|1</mi><mo stretchy="false">⟩</mo> is 

$$
\left|\frac{2 \sqrt{2}}{3}\right|^2 = \frac{8}\{9}=88.9
$$

---
> [!IMPORTANT]
> Some content may have been generated by AI **and manually reviewed**.

