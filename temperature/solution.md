# import
import matplotlib.pyplot as plt
%matplotlib inline

# axis x, axis y
y = [33,66,65,0,59,60,62,64,70,76,80,81,80,83,90,79,61,53,50,49,53,48,45,39]
x = list(range(len(y)))

# plot
plt.plot(x, y)
plt.axhline(y=70, linewidth=1, color='r')
plt.xlabel('hours')
plt.ylabel('Temperature ºC')
plt.title('Temperatures of our server throughout the day')

# assign a variable to the list of temperatures
temperatures_C = [33,66,65,0,59,60,62,64,70,76,80,81,80,83,90,79,61,53,50,49,53,48,45,39]

# 1. Calculate the minimum of the list and print the value using print()
minimum=min(temperatures_C)
print("minimum =",minimum)

# 2. Calculate the maximum of the list and print the value using print()
maximum=max(temperatures_C)
print("maximum =",maximum)

# 3. Items in the list that are greater than 70ºC and print the result
hightemp=[]
for i in temperatures_C:
    if i>=70:
        hightemp.append(i)

print("temperatures higher or equal than 70ºC", hightemp)
        
# 4. Calculate the mean temperature throughout the day and print the result
average=sum(temperatures_C)/len(temperatures_C)
print("mean =",average)

# 5.1 Solve the fault in the sensor by estimating a value

point1=temperatures_C[2]
point2=temperatures_C[4]
position1=2
position2=4

# linear interpolation
fault=(point1)+(3-2)*((point2-point1)/position2-position1)

print("Estimation of the temperature at 03:00 on the list =", fault)

# 5.2 Update of the estimated value at 03:00 on the list
temperatures_new=[]
for i in range(0,len(temperatures_C)):
    if i==3:
        temperatures_new.insert(i,fault)
    else:
        temperatures_new.insert(i,temperatures_C[i])
    
print("Corrected temperatures after estimation: ", temperatures_new)

# Bonus: convert the list of ºC to ºFarenheit
Far=[]
for i in temperatures_new:
    Far.append(32+i*1.8)
print("temperatures in Fahrenheit grades= ",Far)

# Print True or False depending on whether you would change the cooling system or not

counter1=0
counter2=0
counter3=0
for i in temperatures_C:
    if i>=70:
        counter1+=1
    if i>80:
        counter2=1
    if average>65:
        counter3=1

if counter1>4 or counter2==1 or counter3==1:
    print("TRUE")
else:
    print("FALSE")

# 1. We want the hours (not the temperatures) whose temperature exceeds 70ºC

hours=[]
for i in range(0,len(temperatures_C)):
    if temperatures_C[i]>=70:
        hours.append(i)
print(hours)

# 2. Condition that those hours are more than 4 consecutive and consecutive, not simply the sum of the whole set. Is this condition met?
counter=0
for i in range(3,len(temperatures_C)):
    if temperatures_C[i]>=70 and temperatures_C[i-1]>=70 and temperatures_C[i-2]>=70 and temperatures_C[i-3]>=70:
        counter=1
if counter==1:
    print("TRUE")
else:
    print("FALSE")

 # 3. Average of each of the lists (ºC and ºF). How they relate?
average1=sum(temperatures_new)/len(temperatures_new)
print("mean temperature (ºC) =",average1)

average2=sum(Far)/len(Far)
print("mean temperature (ºC) =",average2)

# the relation F=32+1.8*T remains between the averages of both set of temperatures
32+average1*1.8

# 4. Standard deviation of each of the lists. How they relate?

import statistics
import math
st1=statistics.stdev(temperatures_new)
st2=statistics.stdev(Far)

print(st1)
print(st2)
