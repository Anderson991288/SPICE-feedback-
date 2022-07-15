# SPICE-feedback-

## 回授對放大器頻寬的效應

![Screenshot from 2022-07-15 21-31-04](https://user-images.githubusercontent.com/68816726/179233187-da025664-77ab-406f-8854-3b78a0a3b49e.png)

netlist:
```
Effect of Feedback on the Amplifier Bandwidth
* circuit description (Rf=1Meg)*
Vcc+ 3 0 10V
Vcc- 6 0 -10V
Vs 1 0 ac 1 
Ibias 5 6 DC 1m
Rc 3 4 5k
Rf 2 4 1Meg
Rs 1 2 10k
C1 5 0 1GF
* model description
Q1 4 2 5 Q2N3904
.model Q2N3904 npn (Is=6.734f Xti=3 Eg=1.11 Vaf=74.03
+ Bf=416.4 Ne=1.259 Ise=6.734f
+ Ikf=66.78m Xtb=1.5 Br=.7371 Nc=2
+ Isc=0 Ikr=0 Rc=1 Cjc=3.638p Mjc=.3085
+ Vjc=.75 Fc=.5 Cje=4.493p Mje=.2593
+ Vje=.75 Tr=239.5n Tf=301.2p Itf=.4
+ Vtf=4 Xtf=2 Rb=10)
* analysis requests
.ac DEC 100 1Hz 1GHz
.control
run
plot db(v(4))
*output requests
.endc
```

![Screenshot from 2022-07-15 21-32-25](https://user-images.githubusercontent.com/68816726/179233398-eb3557fe-2f12-4abf-84d2-b8f7db32b90e.png)

