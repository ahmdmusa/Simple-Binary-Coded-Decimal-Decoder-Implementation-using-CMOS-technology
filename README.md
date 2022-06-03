# Simple-Binary-Coded-Decimal-Decoder-Implementation-using-CMOS-technology
Simple Binary Coded Decimal  Decoder Implementation using  CMOS technology - Custom design using Cadence virtuoso & (*TCMC65nm*)

### Introduction

![image](https://user-images.githubusercontent.com/66570093/171924942-221c0263-ae92-414c-b633-e71b7b8ed10b.png)

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



BCD Decoder Implementation
3
• Analysis & k-map:


 
# note: we used x to denote to dontcare .
𝑎𝑎 ′= 𝐴𝐴′𝐵𝐵′𝐶𝐶′𝐷𝐷+𝐵𝐵𝐵 ′𝐷𝐷′ 𝑏𝑏 ′=𝐵𝐵(𝐶𝐶′+𝐷𝐷′).(𝐶𝐶+𝐷𝐷) 𝑐𝑐 ′=𝐵𝐵′𝐶𝐶𝐶 ′ 𝑑𝑑 ′=𝐴𝐴′𝐵𝐵′𝐶𝐶′𝐷𝐷+𝐵𝐵𝐵 +𝐵𝐵𝐶𝐶′𝐷𝐷′
e ′= D+BC'
f ′= CB' +CD+A'B'D
g ′= A'B'C'+BCD

•	Circuit diagram (cadence virtuoso): 


![image](https://user-images.githubusercontent.com/66570093/171925795-f6fc76d0-f08f-4842-9ad0-90f885ec36dc.png)




• Sizing:
 According to tech used (tcmc65n) we find minimum W/L ratio
 The main problem is that Bn=! Bp that makes the transfer from logic 1 to logic 0 (region3) taking more time than expected.
 So, we make W/L for nmos = 120n/60n and Lp=60n and sweep the value of wp in Vin-Vout Ch/s curve.
 We find wp at Vo=Vi=0.5vdd, that makes Bn=Bp




![image](https://user-images.githubusercontent.com/66570093/171925897-e71c0351-b7f6-407a-b446-7fca253655c1.png)
![image](https://user-images.githubusercontent.com/66570093/171925916-10cb8a4e-aca7-462f-82a5-011cec9fbdc3.png)




*	Using cadence tool to sweep & compute Wp:


![image](https://user-images.githubusercontent.com/66570093/171926038-83389621-c592-4c79-8525-ce3293fe1fb7.png)
* 	Test bench:
![image](https://user-images.githubusercontent.com/66570093/171926122-5ab6c26a-d04c-4955-8436-b96a661beb74.png)


![image](https://user-images.githubusercontent.com/66570093/171926146-4178b9fa-a2ee-495d-b8be-701ccc915351.png)


Wp=120n ✖✖  vs  Wn=240n ✔✔



![image](https://user-images.githubusercontent.com/66570093/171926196-4f3f9869-70f6-473a-a46c-38c583fa5f13.png)


•	Functions implementation after sizing: 


![image](https://user-images.githubusercontent.com/66570093/171926259-07b88a5a-10b6-4e4c-9df4-d8c23ea9ba8d.png)


![image](https://user-images.githubusercontent.com/66570093/171926295-438967f3-7374-4b23-9723-88fbc09c50b9.png)



![image](https://user-images.githubusercontent.com/66570093/171926325-8238857f-4d2e-4c0d-af54-831c4c703a8a.png)


![image](https://user-images.githubusercontent.com/66570093/171926505-a1ecb134-db95-4fbc-8d94-d9cffbfb3baa.png)


![image](https://user-images.githubusercontent.com/66570093/171926529-ea9129f1-9c37-45cb-9a72-15117cf907f4.png)


![image](https://user-images.githubusercontent.com/66570093/171926551-2567a1c2-8675-47f3-8566-2762974171e5.png)



![image](https://user-images.githubusercontent.com/66570093/171926584-308b4e75-bd22-4fa9-a87a-e2cd0ff3c664.png)


•	Final test bench:
•	Here we use 
o	Vdc =1.2v (according to technology used) 
o	4* Vpluse
   for D (v1=0v ; v2=1v)  - Tpulse=0.5 sec Tperiod =1sec
   for C (v1=0v ;  v2=1v)  - Tpulse=1  sec Tperiod =2sec
   for B (v1=0v ;  v2=1v)  - Tpulse=2  sec Tperiod =4sec
   for A (v1=0v ;  v2=1v)  - Tpulse=4  sec Tperiod =8sec
Then RUN trans Simulation 20 seconds & plot input verses the output!



![image](https://user-images.githubusercontent.com/66570093/171926629-46c99638-5e57-45ff-afd7-9eb92d17f117.png)


•	Run trans simulation for testing : (CSV file s available on our drive)

![image](https://user-images.githubusercontent.com/66570093/171926682-b27ccf6a-6d97-4841-a3d8-ece0a94279eb.png)


* test and compare to the Truth table:


![image](https://user-images.githubusercontent.com/66570093/171926730-699e972f-8bbf-474f-9019-28534c6a96b9.png)


## LAYOUT:

As mentioned before the project is to be divided into 7 blocks to simplify the job of building the whole Ic layout !

* a :

![image](https://user-images.githubusercontent.com/66570093/171926936-0ab70ffb-4e8b-45a1-a972-4cdab8ebbe29.png)


![image](https://user-images.githubusercontent.com/66570093/171926975-51f889c0-691b-47b0-bf11-a27ca1a90d1d.png)


* b :

![image](https://user-images.githubusercontent.com/66570093/171927017-8fd7f162-4d25-410f-b4de-21df6e0a4aad.png)


![image](https://user-images.githubusercontent.com/66570093/171927109-073b572a-483b-420c-ae0e-45bfb8ff1ee9.png)



* c:
 ![image](https://user-images.githubusercontent.com/66570093/171927207-d6aa44fb-04e6-4703-a15c-12c2c6a28868.png)
![image](https://user-images.githubusercontent.com/66570093/171927241-b4bdaa64-9f48-4d21-91ce-7cd68aad166b.png)
 
 
 * d:
 ![image](https://user-images.githubusercontent.com/66570093/171927387-4c8ce9de-13f2-4c53-b7d5-36dfa2a1a48f.png)

![image](https://user-images.githubusercontent.com/66570093/171927432-8652c3c3-047c-415e-8793-a442fa36e5d4.png)
 e:
 ![image](https://user-images.githubusercontent.com/66570093/171927509-49da7392-4767-45a8-bf42-1b8b39d3ddb0.png)

![image](https://user-images.githubusercontent.com/66570093/171927549-903a74d8-edce-4ddf-8cc0-ccc0c604bb59.png)



f:
![image](https://user-images.githubusercontent.com/66570093/171927628-d7cc58ce-031a-426f-8dfe-8c3a1087fac2.png)


![image](https://user-images.githubusercontent.com/66570093/171927668-273b2c29-286a-4b25-a0dd-44769e30acb9.png)


g:
![image](https://user-images.githubusercontent.com/66570093/171927742-6a3b9db5-f951-4046-8726-2a16ab265e24.png)

![image](https://user-images.githubusercontent.com/66570093/171927796-46fdf570-eead-44f2-a83b-521ce5f38b44.png)
![image](https://user-images.githubusercontent.com/66570093/171927815-d2d57a7e-b4f6-4519-898c-4eefb6cfce21.png)
 
 
 inv:
  ![image](https://user-images.githubusercontent.com/66570093/171927864-cf759efc-ed26-4501-b362-fb8a972f1ded.png)
![image](https://user-images.githubusercontent.com/66570093/171927892-60ea9351-4d6b-401c-9d28-5a676a1e0956.png)




•	Full IC Layout :


![image](https://user-images.githubusercontent.com/66570093/171928015-c91c0e91-97b3-47db-91da-cbdfcd41570e.png)
Final area used was around .. (27.4*26.2) um 

![image](https://user-images.githubusercontent.com/66570093/171928081-1c244fc7-bef7-40c3-a28e-4fa4d46d384e.png)
    
    
    
    
    
    




















