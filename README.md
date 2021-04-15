# Qiskit-Graph-state-improvement

Since every qubit has its own relaxation time, too long executing time will cause the result far from the accuracy. Therefore, it is essential to shorten the executing time. Also because different site CZ gates can commute with each other, we can rearrange the order of the CZ gates and find out shortest executing time for the graph state. Moreover, we decompose the CX gate pulse and reconstruct the CZ gate instead of using two hardamard gates and CX gate.





## Graph state class

We create the graph state class to rearrange the CZ gates. One can create the edges list and put it on graph state state class. In the code, we have already put our best result, 0.972, of all tests and corresponding Job ID. 
<img src="/images/backend.png" width="500" height="300">   
<img src="/images/combinations.png" width="550" height="300">  


## CZ_gate pulse

For the CZ gate pulse, in Qiskit, they use the two Hadamard gates and one CX gate to manifest CZ gate. Here, we create a custom CZ gate pulse to replace the default one. Therefore, we don't need to apply few more Hadamard to apply the CZ gates. The way we create our custom CZ gates is to extract the CR pulse from the CNOT gate and recombine it into CZ gate pulse. Because of insufficient tests for custom CZ gate in ibmq-casablanca, we don't turn it on in our code. However, here are some results executing in ibmq-rome and ibmq-bogota. If one want to increase the fidelity of graph state by 1~2 %, one can try to turn it on in stabilizer_measure_circuit function.

<img src="/images/cz_pulse.png" width="600" height="800">   
