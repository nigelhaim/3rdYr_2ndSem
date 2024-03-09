Submitted by: Nigel Haim N. Sebastian 

#### Given 

| Jobs | AT  | BT  | Priority |
| ---- | --- | --- | -------- |
| 1    | 1   | 4   | 6        |
| 2    | 5   | 12  | 2        |
| 3    | 5   | 9   | 4        |
| 4    | 11  | 2   | 3        |
| 5    | 16  | 10  | 1        |
| 6    | 20  | 11  | 5        |
Solve for the **WT, TT, AVE WT & AVE TT**

1. FCFS (First Come First Serve)
2. SJF (Shortest Job First)
3. SRTF (Shortest Remaining Time First)
4. Prio (Priority)
5. RR = 2 (Round Robin with quantitive time (q) = 2)

| /   |     |
| --- | --- |
| 0   | 1   |
#### 1. First Come First Serve (FCFS)

**Gantt Chart**

| J1  | J2  | J3  | J4  | J5  | J6       |
| --- | --- | --- | --- | --- | -------- |
| 1   | 5   | 17  | 26  | 28  | 38    49 |
**WT (Waiting Time)  = WT - AT**

$J1 = 1-1=0$
$J2 = 5-5=0$
$J3 = 17-5=12$ 
$J4 = 26-11=15$
$J5 = 28-16=12$
$J6 = 38 -20 =18$

$AveWT = \frac{12+15+12+18}{6} = 9.5ms$

**TT (Turnaround Time)**

$J1=5-1=4$
$J2 = 17-5=12$
$J3=26-5=21$
$J4 = 28-11=17$
$J5 = 38-16=22$
$J6 = 49-20=29$
$AveTT = \frac{4+12+21+17+22+29}{6}= 17.5 ms$

#### 2. Shortest Job First (SJF)

**Gantt Chart**

| J1  | j3  | J4  | J5  | J6  | J2      |
| --- | --- | --- | --- | --- | ------- |
| 1   | 5   | 14  | 16  | 26  | 37   49 |

$J1 = 1-1=0$
$J2 = 37-5=32$
$J3 =   5-5=0$
$J4 =  14-11=3$
$J5 =  16-16=0$
$J6 = 26-20=6$

$AveWT = \frac{32+3+6}{6} = 6.83ms$

**TT(Turnaround Time)**

$J1 =5-1=4 $
$J2 =49-5=44$
$J3 = 14-5=9$
$J4 = 16-11=5$
$J5 = 26-16=10$
$J6 = 37-20=17$

$AveTT = \frac{4+44+9+5+10+17}{6} = 14.83ms$

#### 3. Shortest Remaining Time First (SRTF)

**Gantt Chart**

| J1  | J3  | J4  | J3  | J5  | J6  | J2      |
| --- | --- | --- | --- | --- | --- | ------- |
| 1   | 5   | 11  | 13  | 16  | 26  | 37   49 |
