![image](https://user-images.githubusercontent.com/66570093/171924942-221c0263-ae92-414c-b633-e71b7b8ed10b.png)

# Simple-Binary-Coded-Decimal-Decoder-Implementation-using-CMOS-technology
Simple Binary Coded Decimal  Decoder Implementation using  CMOS technology - Custom design using Cadence virtuoso & (*TCMC65nm*)

** virtuoso files will be available after evaluation ,

### Introduction

What we are trying to do here is to implement binary coded decimal 4-bit input and 0-9 output, using CMOS 
technology … 


![image](https://user-images.githubusercontent.com/66570093/171916753-0dffa529-a4ad-4c93-bbf4-ea94058aeb46.png)
   
   
   



 * First, we may use the following steps to brainstorm ideas behind the project :

### State the problem

*  getting Truth table  n inputs & m of output
* solve using k map & get function
* state main blocks and design functions using CMOS technology.

### Going deep into design 
  
* calc. sizing parameters using inv and cad tool
* sizing all devices to the main ratio.
* testing and comparing to Truth table 
### Layout 
* building our 7 block functions layout 
* place and routing all blocks into one field
* packaging 




## input 
![image](https://user-images.githubusercontent.com/66570093/171925244-7f5f7102-3e54-428f-ac8f-d103545de589.png)


## BCD Decoder Implementation

• Analysis & k-map:

### Truth Table 

n | **A**| **B**| **C**| **D**| **a**| **b**| **c** | **d**| **e**| **f**| **g**
:--|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:
**0** | 0| 0| 0| 0| 1| 1| 1| 1| 1| 1| 0
**1** | 0| 0| 0| 1| 0| 1| 1| 0| 0| 0| 0
**2** | 0| 0| 1| 0| 1| 1| 0| 1| 1| 0| 1
**3** | 0| 0| 1| 1| 1| 1| 1| 1| 0| 0| 1
**4** | 0| 1| 0| 0| 0| 1| 1| 0| 0| 1| 1
**5** | 0| 1| 0| 1| 1| 0| 1| 1| 0| 1| 1
**6** | 0| 1| 1| 0| 1| 0| 1| 1| 1| 1| 1
**7** | 0| 1| 1| 1| 1| 1| 1| 0| 0| 0| 0
**8** | 1| 0| 0| 0| 1| 1| 1| 1| 1| 1| 1
**9** | 1| 0| 0| 1| 1| 1| 1| 1| 0| 1| 1
**10**| 1| 0| 1| 0| X| X| X| X| X| X| X
**11**| 1| 0| 1| 1| X| X| X| X| X| X| X
**12**| 1| 1| 0| 0| X| X| X| X| X| X| X
**13**| 1| 1| 0| 1| X| X| X| X| X| X| X
**14**| 1| 1| 1| 0| X| X| X| X| X| X| X
**15**| 1| 1| 1| 1| X| X| X| X| X| X| X


########## 

 
#### 𝑎′ = 𝐴𝐴′𝐵𝐵′𝐶𝐶′𝐷𝐷+𝐵𝐵𝐵 ′𝐷𝐷′
#### 𝑏′ = 𝐵𝐵(𝐶𝐶′+𝐷𝐷′).(𝐶𝐶+𝐷𝐷) 
#### 𝑐′ = 𝐵𝐵′𝐶𝐶𝐶 ′
#### 𝑑′ = 𝐴𝐴′𝐵𝐵′𝐶𝐶′𝐷𝐷+𝐵𝐵𝐵 +𝐵𝐵𝐶𝐶′𝐷𝐷′
#### e′ = D+BC'
#### f′ = CB' +CD+A'B'D
#### g′ = A'B'C'+BCD




#### 
##### note: we used x to denote to dontcare .

•	Circuit diagram (using cadence virtuoso) :-  


![image](https://user-images.githubusercontent.com/66570093/171925795-f6fc76d0-f08f-4842-9ad0-90f885ec36dc.png)





•	Final test bench:
•	Here we use 
-	Vdc =1.2v (according to technology used) 
-	4* Vpluse
   -  for D (v1=0v ; v2=1v)  - Tpulse=0.5 sec Tperiod =1sec
   -  for C (v1=0v ;  v2=1v)  - Tpulse=1  sec Tperiod =2sec
   - for B (v1=0v ;  v2=1v)  - Tpulse=2  sec Tperiod =4sec
   - for A (v1=0v ;  v2=1v)  - Tpulse=4  sec Tperiod =8sec
Then RUN trans Simulation 20 seconds & plot input verses the output!



![image](https://user-images.githubusercontent.com/66570093/171926629-46c99638-5e57-45ff-afd7-9eb92d17f117.png)


•	Run trans simulation for testing : (CSV file s available on our drive)

![image](https://user-images.githubusercontent.com/66570093/171926682-b27ccf6a-6d97-4841-a3d8-ece0a94279eb.png)


* test and compare to the Truth table:


![image](https://user-images.githubusercontent.com/66570093/171926730-699e972f-8bbf-474f-9019-28534c6a96b9.png)






•	Full IC Layout :


Final area used was around .. (27.4*26.2) um 

![image](https://user-images.githubusercontent.com/66570093/171928081-1c244fc7-bef7-40c3-a28e-4fa4d46d384e.png)
    
    
    
    
    
    




















