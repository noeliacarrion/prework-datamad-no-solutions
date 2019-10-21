# Assign spell power lists to variables
gandalf = [10, 11, 13, 30, 22, 11, 10, 33, 22, 22]
saruman = [23, 66, 12, 43, 12, 10, 44, 23, 12, 17]
# Assign 0 to each variable that stores the victories
gandalfwins = 0
sarumanwins = 0
tie = 0
# Execution of spell clashes
i = 0
j = 0
for i in range(0,len(gandalf)):
        if gandalf[i]>saruman[i]:
            gandalfwins += 1
        elif gandalf[i]==saruman[i]:
            tie +=1
        else:
            sarumanwins +=1

        
print('Gandalf wins', gandalfwins)
print('Saruman wins', sarumanwins)
# We check who has won, do not forget the possibility of a draw.
# Print the result based on the winner.
if gandalfwins>sarumanwins:
    print('Gandalf wins the battle')
else:
    print('Saruman wins the battle')