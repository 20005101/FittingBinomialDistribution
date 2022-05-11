# Fitting Binomial Distribution
## Aim :
To fit binomial distribution for the given frequencey distribution

image

## Software required :
 Python

## Theory:
The binomial distribution is a discrete probability distribution. It describes the outcome of n independent trials in an experiment. Each trial is assumed to have only two outcomes, either success or failure. If the probability of a successful trial is p, then the probability of having x successful outcomes in an experiment of n independent trials is as follows.

image

The following are criteria for a frequency distribution to be a binomial distribution

The experiment consists of n repeated trials.
Each trial can result in just two possible outcomes (a success anda failure).
The trials are independent (the outcome on one trial does not affect the outcome on other trials).
Procedure :
image

## Program
```
Developed by
Register Number: 212220230037
Name: R K PRAVEEN
import numpy as np
import math
import scipy.stats

X=[0,1,2,3,4,5,6]
f=[13,25,52,68,32,16,4]
n=6
N=np.sum(f)
mean=np.inner(X,f)/N
p=mean/n
q=1-p
Pr=list(); E=list(); xi=list()
print("  X P(X=x) Obs.Fr  Ex.Fre   xi ")
print("----------------------------------")
for x in range(7):
    c=math.factorial(n)/(math.factorial(x)*math.factorial(n-x))
    Pr.append(c*p*x*q*(n-x))
    E.append(Pr[x]*N)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.2f  %4.2f   %3.2f  %3.2f"%(x,Pr[x],f[x],E[x],xi[x]))
print("----------------------------------")
cal_chi2=np.sum(xi)
print("Calculated value of Chi square is %4.2f"%cal_chi2)
tab_chi2=scipy.stats.chi2.ppf(1-.01, df=n)
print("Table value of Chi square at 1  level is %4.2f"%tab_chi2)
if cal_chi2<tab_chi2:
    print("The given data can be fitted in binomial distribution at 1% LOS")
else:
    print("The given data cannot be fitted in binomial distribution at 1% LOS")
 ```
## Output:
![screen 33](https://user-images.githubusercontent.com/77062608/167775587-b7ef2197-87d1-492f-9e8a-bb7327d7157f.jpg)


## Results:
Thus, fitting binomial distribution for the given frequencey distribution is verified.
