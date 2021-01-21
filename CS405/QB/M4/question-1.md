---
layout: default
course: CS405
module: 4
---

#### Consider the five-stage pipelined processor specified by the following reservation table and answer the following. ('s' indicates the stages).

| / |1  |2  |3  |4  |5  |6  |
| --- | --- | --- | --- | --- | --- | --- |
| $$S_1$$ | X |  |  |  |  |X |
| $$S_2$$ |  | X |  | X |  
| $$S_3$$ |  |  | X | 
| $$S_4$$ |  |  |  | X | X |  |


1. List the set of forbidden latencies & the collision vector.
2. Draw the state transition diagram showing all the possible initial sequences without causing a collision in the pipeline.
3. List all the simple and greedy cycles from the state diagram.
4. Determine the minimal average latency (MAL).

##### Answer:

###### 1.Forbidden Latencies and Collision Vector
> Finding the distances between each X in each \\(S_x\\)

\\(S_1 = \\) { (6-1) } = { 5 }  
\\(S_2 = \\)  { (4-2) } = { 2 }  
\\(S_3 = \\)  { (3) } = { 3 }  
\\(S_4 = \\)  { (5-4) } = { 1 }  

> Taking unique values from \\(S_x\\) to form the Forbidden Latency

Forbidden Latency = { 1, 2, 3, 5 }

> Permissible Latencies are the Complement of this set (till the Max Forbidden Latency)

Permissible Latency = { 4 }

> { 6 } is ignored since it is greater.

>Collision vector is a bit value (number of bits corresponds to the max Forbidden Latency)

Collision vector = 


| \\(C_5\\) |\\(C_4\\)  |\\(C_3\\)  |\\(C_2\\)  |\\(C_1\\)  |
| --- | --- | --- | --- | --- |
|1  |0  |1  |1  | 1 |


Collision vector = 10111

---

###### 2. State Diagram

> Draw the collision vector as the start state in the diagram.
> Outward edges depends on the \\(n^{th}\\) place for bit 0 (zero).

> Perform n right shifts and OR it with the original collision vector.

\\(  11011 +(OR) \\\ \dfrac{00001}{10111} \\)

\\( 11011 +(OR) \\\ \dfrac{00010}{10111} \\)

---
###### 3. Simple Cycle

> Simple cycle is a latency cycle where each state only appears **ONCE**

Simple cycle = { 3, 4, 6 }

> Greedy cycle are latency cycles that are all made from minimum latency cycles from the start.

Greedy cycle = { 3 }

---
###### 4.Minimum Average Latency (MAL)

> Atleast one greedy cycle leads to MAL

> 4 has the constant latency that is the minimum average latency

$$\dfrac{3}{1}  = 3$$

Minimum average Latency = 3
