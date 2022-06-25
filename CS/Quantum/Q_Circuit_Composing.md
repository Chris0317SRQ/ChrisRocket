# Qiskit Note
## Reference:
1. Qubit by Qubit of The Coding School
2. Qiskit

## Structure of Quantum Circuit
<div class="sl-block is-focused" data-block-type="image" data-name="image-d4483b" style="width: 790.384px; height: 518px; left: 84.808px; top: 91px; min-width: 1px; min-height: 1px;" data-origin-id="f5584344c261b62b68585b3d05f31cc9"><div class="sl-block-content" style="z-index: 10;"><img style="" data-natural-width="1683" data-natural-height="1103" src="https://s3.amazonaws.com/media-p.slid.es/uploads/1169602/images/9668347/pasted-from-clipboard.png" data-lazy-loaded=""></div></div>

<div class="sl-block is-focused" data-block-type="image" data-name="image-9e6e73" style="width: 976.125px; height: 637.469px; left: -16.125px; top: 74px; min-width: 1px; min-height: 1px;" data-origin-id="31abb7f10fb7cc5eb24f7c0529b35e5a"><div class="sl-block-content" style="z-index: 11;"><img style="" data-natural-width="1274" data-natural-height="832" src="https://s3.amazonaws.com/media-p.slid.es/uploads/1169602/images/9668796/Screenshot_from_2022-06-25_08-12-55.png" data-lazy-loaded=""></div></div>

## Code
### Import
```python
# Basis
import matplotlib.pyplot as plt
import numpy as np
import qiskit as q
from math import pi
from qiskit import *

# Plot data
from qiskit.visualization import plot_histogram
from qiskit.tools.monitor import job_monitor

# Quantum Circuit
from qiskit import QuantumCircuit, ClassicalRegister, QuantumRegister, transpile
from qiskit.tools.visualization import circuit_drawer
from qiskit.quantum_info import state_fidelity

# Simulator
from qiskit import BasicAer

# Tell matplotlib that we are in an Ipython notebook
%matplotlib inline
```

### Designing Circuits
```python
# This creates a quantum circuit object
circ = q.QuantumCircuit(1,1)

# This prints out a diagram of the circuit, the "mpl" makes it look pretty!
display(circ.draw(output="mpl"))

# Linear operation to qubit 0
circ.h(0)
circ.z(0)
circ.h(0)
display(circ.draw(output="mpl"))

# Multi-qubit
circ = q.QuantumCircuit(15,1)
circ.x(6)
display(circ.draw(output="mpl"))

# rz gate
circ.rz(m.pi,0)
display(circ.draw(output="mpl"))

# Call Aer for simulation
backend=q.Aer.get_backend('statevector_simulator')
job = q.execute(circ, backend)
result = job.result()
counts = result.get_counts(circ)
graph = q.visualization.plot_histogram(counts)
display(graph)

# Bell state: Φ+
phi_plus = q.QuantumCircuit(2)
phi_plus.h(0)
phi_plus.cx(0,1)
display(phi_plus.draw(output="mpl")) 

# Bell state: Φ- (Use Built-in Function)
circ_phiminus = QuantumCircuit(2,2)
circ_phiminus.h(0)
circ_phiminus.draw('mpl')
```