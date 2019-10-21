# Assign problem data to variables with representative names
# well height, daily advance, night retreat, accumulated distance
totalheight = 125
dayrise = 30
nightfall = 20
distance = 0

# Assign 0 to the variable that represents the solution
Days = 0

# Write the code that solves the problem
while distance < totalheight:
    Days +=1
    distance = distance + dayrise
    if distance < totalheight:
        distance = distance -nightfall

# Print the result with print('Days =', days)
print('Days =' , Days)