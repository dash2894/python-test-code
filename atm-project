#ATMExcept.py
class DepositError(Exception):pass
class WithDrawError(BaseException):pass
class InSuffFundError(Exception):pass

#ATMMainProject.py
from ATMExcept import DepositError, WithDrawError, InSuffFundError
from ATMMenu import menu
from ATMOperations import deposit,withdraw,balenq
while(True):
    try:
        menu()
        ch=int(input("Enter Ur Choice:"))
        match(ch):
            case 1:
                try:
                    deposit()
                except DepositError:
                    print("\tDON'T TRY TO DEPOSIT -VE/ZERO VALUE")
                except ValueError:
                    print("\tDON'T ENTER ALNUMS,STRS AND SYMBOLS AS DEPOSIT AMOUNT")
            case 2:
                try:
                    withdraw()
                except WithDrawError:
                    print("\tDON'T TRY TO WITHDRAW -VE/ZERO VALUE")
                except InSuffFundError:
                    print("\tUr Account Does not Contain Suff Funds-Read Python Notes")
                except ValueError:
                    print("\tDON'T ENTER ALNUMS,STRS AND SYMBOLS AS WITHDRAW AMOUNT")
            case 3:
                balenq()
            case 4:
                print("Thx for using this Project")
                break
            case _:
                print("\tUR Selection of Operation is Wrong-try again")
    except ValueError:
        print("\tDON'T ENTER ALNUMS,STRS AND SYMBOLS FOR CHOICE:")

#ATMMenu.py
def menu():
    print("-"*50)
    print("\t\tATM OR Funds Transfer Operation")
    print("-" * 50)
    print("\t\t1. Deposit")
    print("\t\t2. Withdraw")
    print("\t\t3. BalEnq")
    print("\t\t4. Exit")
    print("-" * 50)

#ATMOperations.py
from ATMExcept import DepositError,WithDrawError,InSuffFundError
bal=500.00 # here bal is called Global variables
def deposit():
    damt=float(input("Enter UR Deposit Amount:"))#chnace of raising ValueError
    if(damt<=0):
        raise DepositError
    else:
        global bal
        bal=bal+damt
        print("\tUr Account xxxxxx123 Credited with INR:{}".format(damt))
        print("\tUr Account xxxxxx123 Bal after desposit:{}".format(bal))

def withdraw():
    global bal
    wamt = float(input("Enter UR Withdraw Amount:"))  # chnace of raising ValueError
    if(wamt<=0):
        raise WithDrawError
    elif((wamt+500)>bal):
        raise InSuffFundError
    else:
        bal=bal-wamt
        print("\tUr Account xxxxxx123 Debited with INR:{}".format(wamt))
        print("\tUr Account xxxxxx123 Bal after Withdraw:{}".format(bal))

def balenq():
    print("\tUr Account xxxxxx123 Bal:{}".format(bal))
