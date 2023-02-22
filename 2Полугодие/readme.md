
Решения.py
| № | Статус |

|1|+++ |

|2|+++|

|3|

|4|+++|

|5|+++|

|6|  

from turtle import *

left(90)

for i in range(7):

forward(300)
 
 right(120)

pu()

for x in range(1,9):
   
   for y in range(1,10):
  
  goto(x*30,y*30)
     
     dot(5)

done()  |

|7|+++|

|8|+++|

|9|   |

|10|+++|

|11|+++|

|12|         |

|13|+++|

|14|+++|

|15|+++|

|16|         |

|17|         |

|18|         |

|19|+++|

|20|+++|

|21|+++|

|22|         |

|23|         |

|24|+++|

|25|+++|

|26|         |

|27|with open('27-A.txt') as f:
    n=int(f.readline())
    m=([int(x) for x in f][:n]*3)[n//2:-n//2]
pr=[0]*(len(m)+1)
for i in range(1,len(pr)):
    pr[i]=pr[i-1]+m[i-1]
po=[0]*(len(m)+1)
for i in range(len(po)-2, -1,-1):
    po[i]=po[i+1]+m[i]
st=[0]*n
fn=[0]*n
st[0]=sum(pr[:n//2+1])
fn[0]=sum(po[-n//2:])
s1=s2=0
for i in range(1,n):
    s1=m[i-1]*(n//2)+pr[i]
    s2=m[-i]*(n//2-1)+po[-i-1]
    st[i]=st[i-1]+pr[n//2+i]-s1
    fn[-i]=fn[(-i+1)%n]+po[-(n//2+i)]-s2
c=0
m=float('inf')
for i, t in enumerate(zip(st,fn),start=1):
    if sum(t)<m:
        c, m=i, sum(t)
print(c,m)
         |

a=[]
f=open('27-A.txt')
for i in f:
    a.append(int(i))
a.pop(0)
b=len(a)//2
l=len(a)
a=a+a
for i in range(l):
    d=a[i:i+l]
    cost=0
    for x in range(len(d)):
        if x>b:
            ind=l-x
        else: ind=x
        cost=cost+d[x]*ind
    print(cost)

