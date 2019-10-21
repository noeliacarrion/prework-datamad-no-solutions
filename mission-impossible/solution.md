# Variables

dbs = [0, 1, 0, 0, 0, 0, 1, 0, 1, 23, 1, 0, 1, 1, 0, 0, 0, 
       1, 1, 0, 20, 1, 1, 15, 1, 0, 0, 0, 40, 15, 0, 0]
loud=[]

# Show volumes that exceed 10 dBs
for i in dbs:
    if i>10:
        loud.append(i)
        
print(loud)

# Show the moments (indexs of the list) in which a volume exceeds 10 dBs
positions=[]
for i in range(0,len(dbs)-1):
    if dbs[i]>10:
        positions.append(i)
        
print(positions)

# Combine the last two exercises to show the moments when a 
# volume exceeds 10 dBs. HINT: Use the enumerate function
point=0
vect=[]
for i in range(0,len(dbs)-1):
    if dbs[i]>10:
        point=[i, dbs[i]]
        vect.append(point)
        
print(vect)

# Ethan is discovered if two consecutive volumes are greater than 10 dB. Is he safe? 
# HINT: Beware of the extremes, do not have an error of the type
# IndexError: list index out of range

alarmm=0
for i in range(0, (len(dbs))-1):
    if dbs[i]>10 and dbs[i+1]>10:
        alarmm=1

if alarmm==1:
    print("Alarm!")

    # Your code here
pre=dbs
post=[]

for i in range(0, len(dbs)-1):
    if dbs[i]<20:
        post.append(dbs[i])
    elif dbs[i]>20 and i<=30:
        post.append(dbs[i]-12)
    else:
        post.append(dbs[i]-18)
        
print("Pre hacking:", pre)
print("Post hacking", post)
        