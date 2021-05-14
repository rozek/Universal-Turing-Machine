# Universal Turing-Machines #

This repository contains any material required to run the "Universal Turing Machine" published by Marvin Minsky in "Computation: Finite and Infinite Machines. Englewood Cliffs, N.J.: Prentice-Hall, 1967" using Martin Ugarte's "[Turing Machine Simulator](https://turingmachinesimulator.com/)"

It is primarily intended for the author's lecture on the "Foundations of Computer Science" at [Stuttgart University of Applied Sciences](https://www.hft-stuttgart.com/), but may also of interest to others.

A description of "Turing Machines" (TMs) in general and "Universal Turing Machines" (UTMs) in particular can be found on the author's web site ([german version](https://rozek.de/Turing-Machine/index_de.html), [english version](https://rozek.de/Turing-Machine/index_en.html))

The actual UTM shown here is basically a direct port of a Python implementation by Pontus Johnson (which can be found [in another Github repository](https://github.com/intrinsic-propensity/turing-machine))

However, in order to be run using Martin Ugarte's Turing Machine Simulator, the port had to be prefixed with a "preamble" which places the read/write head of the UTM at a position where Marvin Minsky's UTM implementation expects it to be in the beginning.

In the same way as in the original Python implementation, the port also differentiates between

* state transitions explicitly mentioned in Marvin Minsky's simplified state diagram for his UTM,
* additional (implicitly assumed) state transitions not mentioned in the diagram, but required for the UTM to operate and
* additional (implicitly assumed) state transitions not mentioned in the diagram, which are not needed for the intended operation of the UTM but in fact making the UTM vulnerable to attacks (as described in Pontus Johnson's article "[Intrinsic Propensity for Vulnerability in Computers? Arbitrary Code Execution in the Universal Turing Machine](https://arxiv.org/abs/2105.02124)")

This repository contains the following files

* Marvin-Minsky-UTM.txt<br>
containing a "program" prepared for the Turing Machine Simulator, which implements Marvin Minsky's UTM and may be used to simulate other TMs
* example.txt
with a trivial example illustrating the operation of an UTM. This example may only be run using "Marvin-Minsky-UTM.txt"
* Marvin-Minsky-UTM_attackable.txt<br>
containing the same UTM as above, but with a preamble, that places the read/write head at the required position in the presence of an attack (as described by Pontus Johnson)
* attack.txt
with the initial contents of the UTM's tape in order to run an attack. This example may only be run using "Marvin-Minsky-UTM_attackable.txt"
