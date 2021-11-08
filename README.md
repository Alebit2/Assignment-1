# Assignment-1

import sys
# import sys gives the code a way to stop if the answer in 'no'
list = []
# the list is initially empty but it will be filled.
compounds = {'Hydrogen': 1.008, 'Helium': 4.003, 'Lithium': 6.94, 'Beryllium': 9.01}
# the dictionary above contains the first few elements and their RMM, just in
# case one of them happens to be the chosen element
answer = input('Hello, would youlike to make a solution?: ') 
# The possible answers to the above input are 'yer' or 'no'
if answer == 'yes':
    volume = float(input('Great! what volume do you want to add? (in ml): '))
    b = volume
    a = 0
elif answer == 'no':
    while True:
        print('Alright then, back to sleep I go')
        sys.exit(123)
# The 9 lines above tell the PC that upon a 'yes', it can proceede and ask what
# the preferred volume is. If the answer is 'no', the 'while True' command causes
# the program to print a statement and execute the sys.exit(123) command, 
# stopping and giving error code 123. The volume is also turned into a float()
# value to make sure decimals don't give a TypeError
if b > a:
    list.append(b)
    for key in compounds.items():
        print(key)
    compound = input('Do you want to add any of the above elements?: ')
else:
    print('does not compute')
# In these lines above, the volume (associated to variable 'b') is compared to
# the variable 'a', with value '0' assigned to it. If the volume is lower than
# 0, the PC will let the user know. If the volume is greater than 0, it added 
# to the list of ingredients (list = []) and the 'compounds' dictionary is
# printed iwht a 'for' loop sequence in order to make the keys ad their associated
# values easier to read. After that, the machine asks if the user wants to add
# one of the already present elements in the list. The possible answers are 'yes'
# and 'no'.
if compound == 'yes':
    presentcompound = input('Which one? (type full name): ')
    presentRMM = input('What is the associated RMM?: ')
    list.insert(0, presentcompound), list.append(presentRMM)
    print('List of ingredients:'), print(list)
    conc = input('What is the desired concentration (g/ml): ')
    list.append(conc)
    print('List of ingredients (value, compound/element , RMM , concentration):')
for n in range(len(list)):
        print(list[n])
# Upon a 'yes', the machine asks to input the name and RMM of the chosen element.
# After that, it stores them in the list of ingredients (list = []), and actually
# inserts the name of the element as the first item in the list. this is done to
# ease the reading of the final list of ingredients before the calcuations are
# made. The machine subsequently asks for the desired concentration which it
# proceedes to sotre in the list of ingredients. At the end of the process, the
# machine prints out the list with a 'for' loop so that all the itams appear in
# a column and are easier to read.
if compound == 'no':
    name = input('what is the name of the compound/element?: ')
    list.insert(0, name)
    RMM = input('what is its RMM?: ')
    list.append(RMM)
    compounds.update({name: RMM})
    print('List of ingredients:'), print(list)
    conc = input('What is the desired concentration (g/ml): ')
    list.append(conc)
    print('List of ingredients (compound/element, volume , RMM , concentration):')
for n in range(len(list)):
        print(list[n])
# The 12 lines above are used in case the user types 'no' to the input on line
# 26. Through an 'if' command, the machine asks name and RMM of the compound/element,
# which are then added to the list of ingreeients and also saved on the dictionary
# for later use, though the 'compounds.update({name: RMM})' command, in case
# the user wats to use the same element/compound for the second solution. The 
# program uses the same 'for' loop in line 45 to print out the list of ingredients.
x = float(list[1])
y = float(list[3])
z = float(list[2])
# All the values needed for the calculations are assigned to the above variables
# from the list of ingredients and turned into float() values, so the machine
# can still use them even if they are decimal numbers without reporting any
# TypeError.
moles = x * y
moles = float(moles)
print('the moles are: ', moles)
# Firstly, the moles are calculated by multiplying the values for concentration
# and volume together. Even the 'moles' variable is turned into a float() value
# in case it comes out as a decimal number. The value is then printed for the 
# user to see and make sure no mistakes have been made.
grams = moles * z
print('You will need to add:',grams,'grams of',list[0],'to 1000ml of water \nto get the desired concentration of',x,'g/ml')
list.remove(b)
list.remove(RMM)
list.remove(name)
list.remove(conc)
# The grams are finally calculated through the product between the moles and the
# compound's/element's RMM. The machine then prints a text that instructs on how
# many grams of the selected material need to be added to 1000ml of water to
# obtain the desired concentration. The following 4 lines are 'list.remove() 
# commands needed to clear the list of ingredients for the next solution, provvided
# the user wants to make a second one.
answer3 = input('Do you want to make another solution?: ')
if answer3 == 'yes':
    volume2 = float(input('Great! what volume do you want to add? (in ml): '))
    c = volume2
    d = 0
else:
    answer3 == 'no'
    while True:
        print('Alright then, back to sleep I go')
        sys.exit(123)
# The 9 lines above, and the following ones, are the same as the ones from the 
# first eiteration. The machine asks the same first question.
# The only difference lies in how some variable have changed
# name ('answer' to 'answer3', or 'volume' to 'volume2') in order to avoid
# repetition.
if b > a:
    list.append(c)
    for key in compounds.items():
        print(key)
    compound = input('Do you want to add any of the above elements?: ')
else:
    print('does not compute')
if compound == 'yes':
    presentcompound = input('Which one? (type full name): ')
    presentRMM = input('What is the associated RMM?: ')
    list.insert(0, presentcompound), list.append(presentRMM)
    print('List of ingredients:'), print(list)
    conc = input('What is the desired concentration (g/ml): ')
    list.append(conc)
    print('List of ingredients (value, compound/element , RMM , concentration):'), print(list)
if compound == 'no':
    name = input('what is the name of the compound/element?: ')
    list.insert(0, name)
    RMM = input('what is its RMM?: ')
    list.append(RMM)
    compounds.update({name: RMM})
    print('List of ingredients:'), print(list)
    conc = input('What is the desired concentration (g/ml): ')
    list.append(conc)
    print('List of ingredients (compound/element, volume , RMM , concentration):')
for n in range(len(list)):
        print(list[n])
x = float(list[1])
y = float(list[3])
z = float(list[2])
moles = x * y
moles = float(moles)
print('the moles are: ', moles)
grams = moles * z
print('You will need to add:',grams,'grams of',list[0],'to 1000ml of water \nto get the desired concentration of',x,'g/ml')
list.remove(c)
list.remove(RMM)
list.remove(name)
list.remove(conc)
print('Thank you for using me :)')
