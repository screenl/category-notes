    I understand the ground rules and agree to abide by them. I will not share answers or assist another student during this exam, nor will I seek assistance from another student or attempt to view their answers.


# Problem 1
a. 
| Cache A    | Cache B | Cache C |
| -------- | ------- | -- |
| Invalid  |     any valid combination of two states |
| Modified | Invalid    | Invalid |
| Exclusive| Invalid   | Invalid |
| Shared   | Shared/Invalid | Shared/Invalid |

b. A four-way hyper-threading core can run 4 threads at the same time while a superscalar core can only run one.

c. Coherence protocols can only guarantee the consistency of a single read/write operation in the cache. However, a thread might want to ensure the consistency of memory during more than one operation. For example, a thread may first read and then write to a location based on the value read, but cache cohenrence alone cannot guarantee that the location is not modified between the read and the write.

# Problem 2
a. The spans for (a) are:
    
    1 -> 2 -> 3 -> 5 -> 7
    1 -> 2 -> 3 -> 6 -> 7
    1 -> 4 -> 3 -> 5 -> 7
    1 -> 4 -> 3 -> 6 -> 7

with length 5.

b. The span for (b) is:

    1 -> 3 -> 4 -> 6 -> 7

with length 5.

c. We have the **span law**: $T_p \ge T_\infty$. That is, as we increase the number of cores, the fastest possible execution time tends to the span.

d. 

A : 1, 2, 6

B : 4, 3, 5, 7

Schedule:

    time 1: 1
    time 2: 2, 4
    time 3: 3
    time 4: 5, 6
    time 5: 7

The speedup is $7/5 = 1.4$ (which is maximal because the span of (a) is $5$).

e.

A: 1, 3, 4, 6, 7

B: 2, 5

Schedule:

    time 1: 1
    time 2: 2, 3
    time 3: 4, 5
    time 4: 6
    time 5: 7

The speedup is $7/5 = 1.4$ (which is maximal because the span of (b) is $5$).

# Problem 3
a. 

1. Assuming that there are $I$ instructions

**P1**:

$$t_1 = (0.3 * 4 + 0.5 * 6 + 0.2 * 8) I / (4e9)= 1.45 e (-9)I \ s$$
$$t_2 = (0.3 * 4 + 0.2 * 6 + 0.5 * 8)I / (4e9)= 1.6 e (-9)I\ s$$
$$t_3 = (0.5 * 4 + 0.3 * 6 + 0.2 * 8)I / (4e9)= 1.35 e (-9)I\ s$$

C3 is therefore the fastest.

**P2**:

$$t_1 = (0.3 * 2 + 0.5 * 4 + 0.2 * 3) I / (2e9)= 1.6e (-9)I \ s$$
$$t_2 = (0.3 * 2 + 0.2 * 4 + 0.5 * 3) I / (2e9)= 1.45 e (-9)I\ s$$
$$t_3 = (0.5 * 2 + 0.3 * 4 + 0.2 * 3) I / (2e9)= 1.4 e (-9)I\ s$$
C3 is therefore the fastest.

2. Different cores may have different numbers of execution units and different superscalar abilities. 

b. False. There are no critical sections in MPI due to the fact that processes are not
sharing the memory among each other.

c. 

1. Process 0 : `x = 1`. Process 1 : `x = 3`. Process 2 : `x = 5`. Because the only modified data is `y` in process 2.
2. Process 0 : `y = 0`. Process 1 : `y = -2`. Process 2 : `y = 6`. Because the `y` of process 2 is set to $\max\{1,-2,6\} = 6$.
3. Process 0 : `z = 7`. Process 1 : `z = 7`. Process 2 : `z = 6`. Because the only modified data is `y` in process 2.
4. Process 0 : `x = 1`. Process 1 : `x = 3`. Process 2 : `x = 5`. Because the only modified data is `z` in process 2.
5. Process 0 : `y = 0`. Process 1 : `y = -2`. Process 2 : `y = 6`. Because the only modified data is `z` in process 2.
6. Process 0 : `z = 7`. Process 1 : `z = 7`. Process 2 : `z = 7`. Because the `z` of process 2 is set to $\max\{0,7,6\} = 7$.