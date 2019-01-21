# Setting-Up-Your-Budget
This program is developed for those who have got a little bit expertise using Lists, and output formats have been used to maintain 
the cemetery of data and its alignment being displayed on console. It would provide good understanding on small menu based program 
on console.

#budgeting system
menu="\nBudgeting System\n================\n 1. Distribute your budget\n 2. View your spendings\n 3. View children fee\n 4. View eating-in & eating out\n 5. Exit"
import sys
import os
spendings=[]
year=[]
month=[]
#os.system('clear')
while True:
    try:
        budget=0
        bills=0
        fee=0
        grocery=0
        greengrocery=0
        houserental=0
        tspending=0
        total=0
        choice=0

        print(menu)
        choice=int(input("\nenter your choice:"))
        if (choice!=1 or choice!=2 or choice!=3 or choice!=4 or choice!=5):
            print("Choices must be within 1 to 5. Single Digits only.")
    except ValueError:
        print("Data must be integer to input your choice.")
        
    if choice==1:
        try:
            YEAR=int(input("\nenter year for which you are budgeting: "))
            year.append(YEAR)
        except ValueError:
            print("Data for year must be Integer not decimals!")
            YEAR=int(input("\nenter year for which you are budgeting: "))
            year.append(YEAR)
            
        budget=int(input("enter amount to distribute: "))
        spendings.append(budget)
        print("you have RS.",budget,"in hand")
        bills=int(input("enter amount for utility bills: "))
        spendings.append(bills)
        total=budget-bills
        print("you have RS.",total,"in hand")
        fee=int(input("enter amount for school fee: "))
        spendings.append(fee)
        total=budget-bills-fee
        print("you have RS.",total,"in hand")
        grocery=int(input("enter amount for grocery: "))
        spendings.append(grocery)
        total=budget-bills-fee-grocery
        print("you have RS.",total,"in hand")
        greengrocery=int(input("enter amount for green-grocery: "))
        spendings.append(greengrocery)
        total=budget-bills-fee-grocery-greengrocery
        print("you have RS.",total,"in hand")
        houserental=int(input("enter amount for house-rental: "))
        spendings.append(houserental)
        oilgas=int(input("enter amount for oil & gas consumption: "))
        spendings.append(oilgas)
        total=budget-bills-fee-grocery-greengrocery-houserental-oilgas
        eatinout=int(input("enter amount for eatin and eatout: "))
        spendings.append(eatinout)
        total=budget-bills-fee-grocery-greengrocery-houserental-oilgas-eatinout
        spendings.append(total)
        tspending=budget-total
        spendings.append(tspending)
        print("you have RS.",total,"in hand")
    elif choice==2:
        try:
            print("\n")
            print("Your Earning Distribution for the Year ",year[0])
            print("================================================")
            print("Total Budget  |",'{:5d}'.format(spendings[0]))#'{:05d}'.format(value)
            print("Utility Bills |",'{:5d}'.format(spendings[1]))
            print("School Fee    |",'{:5d}'.format(spendings[2]))
            print("Grocery       |",'{:5d}'.format(spendings[3]))
            print("Green Grocery |",'{:5d}'.format(spendings[4]))
            print("House Rental  |",'{:5d}'.format(spendings[5]))
            print("Oil & Gas     |",'{:5d}'.format(spendings[6]))
            print("Eat in & Out  |",'{:5d}'.format(spendings[7]))
            print("Total Spending|",'{:5d}'.format(spendings[9]),"\n")
            print("you have Saved RS.",'{:5d}'.format(spendings[8]),"\n")
            #print("your spending is: ",spendings[0])
        except IndexError:
            print("There is an error, reading data from the fields. \nFailing to read from Arrays. \nRun option 1 first.\n")
    elif choice==3:
        try:
            print("\n")
            print("Your Earning Distribution for Children Fee Only:")
            print("================================================")
            print("Total Budget  |",spendings[0])
            print("School Fee    |","",spendings[2])
        except IndexError:
            print("There is an error, reading data from the fields. \nFailing to read from Arrays. \nRun option 1 first.\n")
    elif choice==4:
        try:
            print("\n")
            print("Your Earning Distribution for Eating-in & Eating Out:")
            print("=====================================================")
            print("Total Budget  |",spendings[0])
            print("Eat in & Out  |","",spendings[7])
        except IndexError:
            print("There is an error, reading data from the fields. \nFailing to read from Arrays. \nRun option 1 first.\n")
    elif choice==5:
        print("Thanks for using the system.")
        sys.exit(1)

