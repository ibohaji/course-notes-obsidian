---
week: "1"
subject: RL2 - Non-deterministic Finite Automata (NFA)
related: "[[RL1 - Deterministic Finite Automata (DFA)]]"
---
## NFA


```
Non determinstic Finite Automata (NFA) differs from a Determinstic Finite Automota (DFA) in the sense that it can be at multiple states at once.
```


an NFA consists of: 

- A finite set of states, denoted Q.
- A finite set of input symbols, denoted $\Sigma$.
- A transition function that takes states and input symbol as arguments, and return a zero, one or a set of states, denoted $\delta$.
- A start state, one of the states in Q. 
- A set of final or accepting states F, F is a subset of Q.

$$ \Huge
	 A = (Q,\Sigma, \hat{\delta}(, q_0, F)
	 $$
	Contradictory to the [[RL1 - Deterministic Finite Automata (DFA)]] , if a string w is consumed which doesn't lead to an accepting state or any other state, does not prevent it from being accepted by the NFA as a whole.


if 	 $A = (Q,\Sigma,  \hat{\delta}, q_0, F)$ is an NFA , then 
$$
L(A) = \{w \mid \delta(q_0, w) \cap F \neq \emptyset\}

$$
is a set of strings w in $\Sigma^*$ such that $\hat{\delta}(q_0,w)$ contains at least one accepting state. 


---
## Equivalence of DFA and NFA 

The smallest DFA that can be constructed by converting from an NFA is $$\Huge 2^n$$where n is the number of states in the NFA. 


### Method

Initial NFA 

| state | 0 | 1 |
| ---- | ---- | ---- |
| $\to q_0$ | $\{q_0,q_1\}$ | $\{q_0\}$ |
| $q_1$ | $\emptyset$ | $\{q_2\}$ |
| $* q_2$ | $\emptyset$ | $\emptyset$ |
|  |  |  |
1. Construct a subset of the NFA in a table.

| state              | 0             | 1             |
| ------------------ | ------------- | ------------- |
| $\emptyset$        | $\emptyset$   | $\emptyset$   |
| $\to \{q_0\}$      | $\{q_0,q_1\}$ | $\{q_0\}$     |
| $\{q_1\}$          | $\emptyset$   | $\{q_2\}$     |
| $*\{q_2\}$         | $\emptyset$   | $\emptyset$   |
| $\{q_0,q_1\}$      | $\{q_0,q_1\}$ | $\{q_0,q_2\}$ |
| $*\{q_0,q_2\}$     | $\{q_0,q_1\}$ | $\{q_0\}$     |
| $*\{q_1,q_2\}$     | $\emptyset$   | $\{q_2\}$     |
| $*\{q_0,q_1,q_2\}$ | $\{q_0,q_1\}$ | $\{q_0,q_2\}$ |

3. for each subset, rename them such that each subset of states is a new state.

| state | 0 | 1 |
| ---- | ---- | ---- |
| A | $\emptyset$ | $\emptyset$ |
| $\to B$ | $\{q_0,q_1\}$ | $\{q_0\}$ |
| C | $\emptyset$ | $\{q_2\}$ |
| *D | $\emptyset$ | $\emptyset$ |
| E | $\{q_0,q_1\}$ | $\{q_0,q_2\}$ |
| *F | $\{q_0,q_1\}$ | $\{q_0\}$ |
| *G | $\emptyset$ | $\{q_2\}$ |
| *H | $\{q_0,q_1\}$ | $\{q_0,q_2\}$ |


---
**NOTE**

```
Every subset containing an accepting state in the NFA, is also an accepting state in the constructed DFA.

```

---
