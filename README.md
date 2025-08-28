# Lab 1

## Tasks

- Initialize `|0⟩ = {1,0}` and `|1⟩ = {0,1}`.
  - Verify measurements always return 0 and 1.
- Prepare `{0.866, 0.5}`.
  - Verify normalization.
  - Measure 1000 times and compare to theory.
- Prepare `|+⟩ = {0.707, 0.707}`.
  - Measure 1000 times → expect ~50/50.

## Installation

Create a virtual environment and install the dependencies. Use your preferred way to create an environment.

You can use the following as a guide to create a virtual environment:

### On Linux/Mac (bash/zsh)

```bash
python3 -m venv .venv
source venv/bin/activate
```

### On Windows (Powershell)

```powershell
python3 -m venv .venv
.venv\Scripts\Activate.ps1
```

### On Windows (Command Prompt)

```powershell
python3 -m venv .venv
.venv\Scripts\activate.bat
```

Install the required packages.

```bash
python3 -m pip install .
```

## Usage

`state.py` provides the implementation of our quantum simulation.

To initialize a circuit with 2 qubits and 2 classical bits, create a state as follows.

```python
from state import State

state = State(n_qubits=2, n_bits=2)
```

Check the script for implemented gates and how to use them. As an example, you can apply a T Gate on a qubit as follows.

```python
from state import State

# Create a single qubit circuit
state = State(1)

# Apply T Gate, which doesn't affect |0⟩ but changes the phase of |1⟩ by pi/4
state.t(0)

# Measure the value on the qubit
state.measure(0)
```

Use `print` to print the quantum state.

```python
print(state)

# Outputs as follows
"""
>>> print(state)
Quantum state:
0: 1.00+0.00j
1: 0.00+0.00j
"""
```
