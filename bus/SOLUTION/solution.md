# variables

stops = [(10, 0), (4, 1), (3, 5), (3, 4), (5, 1), (1, 5), (5, 8), (4, 6), (2, 3)]

# 1. Calculate the number of stops.
len(stops)

# 2. Assign a variable a list whose elements are the number of passengers in each stop: 
# Each item depends on the previous item in the list + in - out.
total=[0, 0, 0, 0, 0, 0, 0, 0, 0]
j=0
for i in stops:
    if j==0:
        total[j] = (i[0])-(i[1])
    else:
        total[j] = (i[0])-(i[1]) + total[j-1]
    j += 1
print(total)

# 3. Find the maximum occupation of the bus.
max(total)

# 4. Calculate the average occupation. And the standard deviation.
average = sum(total)/len(total)
import statistics
print(average)
print(statistics.pstdev(total))

