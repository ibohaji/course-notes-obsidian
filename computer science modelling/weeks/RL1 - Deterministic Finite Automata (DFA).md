---
week: "1"
subject: RL1 - Deterministic Finite Automata (DFA)
---


## DFA 

```
A Determinstic Finite Automata can only be at a single state at once, at which an automaton can transition from one state to the other given a defined input. 
```


A DFA consists of 

- A finite set of states, denoted Q.
- A finite set of input symbols, denoted $\Sigma$.
- A transition function that takes states and input symbol as arguments, and return a state, denoted $\delta$.
- A start state, one of the states in Q. 
- A set of final or accepting states F, F is a subset of Q.

	$$ \Huge
	 A = (Q,\Sigma, \delta, q_0, F)
	 $$
	
# DFA graph A

```dot 
digraph DFA {
    rankdir=LR; // Lay out the graph horizontally
    node [shape = circle,  fontname="Helvetica"]; 
    edge [fontname="Helvetica",color="white"]; // Default edge style
	bgcolor="transparent";
	
    // States
    S0 [label="S0\nStart", fontcolor="white",color="white"]; 
    S1 [label="S1",fontcolor="white",color="white"];
    S2 [label="S2",fontcolor="white",color="white"]; 
	S3 [label="S3\nAccept",  shape="doublecircle",color="white",fontcolor="white"];
    // Transitions
    S0 -> S1 [label="a",fontcolor="white"];
    S1 -> S2 [label="b",fontcolor="white"];
    S2 -> S3 [label="a",fontcolor="white"];
    S2 -> S2 [label="b",fontcolor="white"];

    // Beautification
    label="Simple DFA Example";
    fontsize=20;
    fontname="Helvetica";
    fontcolor="white";
}

```

$$ \Huge 
	A = (\{S_0,S_1,S_2,S_3\},\{a,b\},\delta, S_0,\{S_3\})

$$
