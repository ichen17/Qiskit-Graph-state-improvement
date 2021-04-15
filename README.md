# Qiskit-Graph-state-improvement

Since every qubit has its own relaxation time, too long executing time will cause the result far from the accuracy. Therefore, it is essential to shorten the executing time. Also because different site CZ gates can commute with each other, we can rearrange the order of the CZ gates and find out shortest executing time for the graph state. Moreover, we decompose the CX gate pulse and reconstruct the CZ gate instead of using two hardamard gates and CX gate.

## Graph state class

We create the graph state class to rearrange the CZ gates. One can create the edges list and put it on graph state state class.

## CZ_gate pulse
