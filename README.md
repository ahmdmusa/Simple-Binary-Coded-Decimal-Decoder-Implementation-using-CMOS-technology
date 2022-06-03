# Simple-Binary-Coded-Decimal-Decoder-Implementation-using-CMOS-technology
Simple Binary Coded Decimal  Decoder Implementation using  CMOS technology - cadence virtuoso 


## Introduction
What we are trying to do here is to implement binary coded decimal 4-bit input and 0-9 output, using CMOS 
technology …
    First, we may use the following flow diagram to brainstorm ideas behind the project :
![image](https://user-images.githubusercontent.com/66570093/171916259-1af0536b-5c32-456a-972d-e4f7da4799fa.png)

![image](https://user-images.githubusercontent.com/66570093/171916753-0dffa529-a4ad-4c93-bbf4-ea94058aeb46.png)




n | A| B| C| D| a| b| c| d| e| f| g
--|--|--|--|--|--|--|--|--|--|--|--

0 | 0| 0| 0| 0| 1| 1| 1| 1| 1| 1| 0
1 | 0| 0| 0| 1| 0| 1| 1| 0| 0| 0| 0
2 | 0| 0| 1| 0| 1| 1| 0| 1| 1| 0| 1
3 | 0| 0| 1| 1| 1| 1| 1| 1| 0| 0| 1
4 | 0| 1| 0| 0| 0| 1| 1| 0| 0| 1| 1
5 | 0| 1| 0| 1| 1| 0| 1| 1| 0| 1| 1
6 | 0| 1| 1| 0| 1| 0| 1| 1| 1| 1| 1
7 | 0| 1| 1| 1| 1| 1| 1| 0| 0| 0| 0
8 | 1| 0| 0| 0| 1| 1| 1| 1| 1| 1| 1
9 | 1| 0| 0| 1| 1| 1| 1| 1| 0| 1| 1
10| 1| 0| 1| 0| X| X| X| X| X| X| X
11| 1| 0| 1| 1| X| X| X| X| X| X| X
12| 1| 1| 0| 0| X| X| X| X| X| X| X
13| 1| 1| 0| 1| X| X| X| X| X| X| X
14| 1| 1| 1| 0| X| X| X| X| X| X| X
15| 1| 1| 1| 1| X| X| X| X| X| X| X





