# Qiskit-Graph-state-improvement

In the design of our circuit, the execution time to complete a cycle of the circuit should be controlled in a small amount of time due to different relaxation time of each qubit. 
Therefore, it is critical to shorten the execution time in order to effectively operate the qubits and optimize the measurement results. 
In our circuit, the CZ gates on different sites communicate with each other, therefore, we rearrange the order of the CZ gates in order to find the graph state with the shortest execution time.
Moreover, we decompose the CX gate pulse and reconstruct the CZ gate instead of using two hardamard gates and CX gate.





## Graph state class

We create the graph state class to rearrange the CZ gates. One can create the edges list and put it on graph state state class. In the code, we have already put our best result, 0.972, of all tests and corresponding Job ID. 
<img src="/images/backend.png" width="500" height="300">   
<img src="/images/combinations.png" width="500" height="300">  


## CZ_gate pulse

For the CZ gate pulse, in Qiskit, they use the two Hadamard gates and one CX gate to manifest CZ gate. Here, we create a custom CZ gate pulse to replace the default one. Therefore, we don't need to apply few more Hadamard to apply the CZ gates. The way we create our custom CZ gates is to extract the CR pulse from the CNOT gate and recombine it into CZ gate pulse. Because of insufficient tests for custom CZ gate in ibmq-casablanca, we don't turn it on in our code. However, here are some results executing in ibmq-rome and ibmq-bogota. If one want to increase the fidelity of graph state by 1~2 %, one can try to turn it on in stabilizer_measure_circuit function.

<img src="/images/cz_pulse.png" width="600" height="800">   
