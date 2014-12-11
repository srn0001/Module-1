Module-1
========
# -*- coding: utf-8 -*-
"""
Spyder Editor

This temporary script file is located here:
/home/sathyanarayan/.spyder2/.temp.py
"""
import math
import numpy
ms=50
g=9.81
rho=1.091   
A=3.1415926*.5*.5
ve=325
Cd=0.15
dt=0.1
tmax=10
dmp=20
i=0
hold=0.0
Vold=0.0
mpold=100


for i in range(1,501):
    t=float(i)/10.0
    if (t<=5.0):
        dmp=20
    else:
        dmp=0
        
    hnew=hold+dt*Vold    
    alp=ms+mpold
    beta=0.5*rho*Vold*abs(Vold)*A*Cd    
    Vnew=((dt*(-alp*g+ve*dmp-beta))/alp)+Vold
    mpnew=mpold-dmp*dt
    hold=hnew
    Vold=Vnew
    mpold=mpnew
    print t, Vnew
        


