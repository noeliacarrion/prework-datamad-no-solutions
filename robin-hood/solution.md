# Variables

points = [(4, 5), (-0, 2), (4, 7), (1, -3), (3, -2), (4, 5),
          (3, 2), (5, 7), (-5, 7), (2, 2), (-4, 5), (0, -2),
          (-4, 7), (-1, 3), (-3, 2), (-4, -5), (-3, 2),
          (5, 7), (5, 7), (2, 2), (9, 9), (-8, -9)]

quadrant1=0
quadrant2=0
quadrant3=0
quadrant4=0
quadrants=[]
distance=0
mindistance=100
minpoint=0

# 1. Robin Hood is famous for hitting an arrow with another arrow. Did you get it?

# True, there are two arrows that hit on the point (5,7)

# 2. Calculate how many arrows have fallen in each quadrant.
for i in points:
    if i[0]>0 and i[1]>0:
        quadrant1+=1
    elif i[0]<0 and i[1]>0:
        quadrant2+=1
    elif i[0]<0 and i[1]<0:
        quadrant3+=1
    elif i[0]>0 and i[1]<0:
        quadrant4+=1

quadrants=[quadrant1, quadrant2, quadrant3, quadrant4]
print(quadrants)

# 3. Find the point closest to the center. Calculate its distance to the center
# Defining a function that calculates the distance to the center can help.
import math

for i in points:
    distance=math.sqrt((i[0]**2)+(i[1]**2))
    if distance<mindistance:
        mindistance=distance
        minpoint=i

print(minpoint)       
print(mindistance)

# 4. If the target has a radius of 9, calculate the number of arrows that 
# must be picked up in the forest.

# only the arrows that are located on the ninth coordinate either in vertical or horizontal direction:
out=[]
for i in points:
    if i[0]==9 or i[0]==-9 or i[1]==9 or i[1]==-9:
        out=i
        print(out)
        
print(counter)