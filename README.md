# ATM
this is atm project on python lsnguage
class BankAccount:
#creating a constructor
    def __init__(self,name,account_number,balance=0):
          self.__name=name
          self.__account_number=account_number
          self.__balance=balance #private attributes

 #for depositing amount
     def deposit(self,amount):
         self.__balance+=amount
         print("Amount is deposited")

  #for withdrawl
      def withdrawl(self,amount):
          if amoun<=self.__balance:
             self.__balance-=amount
             print("Amount is debited")
          else:
             print("Amount insufficient")

       def get_account number(self):
            return self.__account number

    class ATM:
       def __init__(self,account):
             self.account=account
       def show_menu(self):
             print("\n---ATM---")
             print("1. Check Balance")
             print("2. Deposit Money")
             print("3. withdrawl Money")
             print("4. Transfer Money")
             print("5. View account info")
             print("6. Exit")

        def run(self):
            while True:
                self.show_menu()
                choice=input("choose an option")

                if choice=='1':
                      print(f"Your balance is:{self.account.get_balance()})
                elif choice=='2':
                      amount=float(input("enter amount to deposit:"))
                      self.account.deposit(amount)
                      print("f"deposited{amount}.New balance is {Self.account.get_balance()}.")

                elif choice=='3':
                      amount=float(input("enter amount to withdraw:"))
                      self.account.withdraw(amount)
                      print("f"withdra{amount}.New balance is {Self.account.get_balance()}.")

                 elif choice=='4':
                      account_number=input("enter account number to transfer to:")
                      amount=float(input("enter amount to transfer:"))
                      #simulate ti finding the other account
                      other_account=BankAccount("Recipient",account_number)
                      self.account.transfer(amount,other_account)
                      print(f"transferred{amount} to account {account_number}.New balance is {self.account.get_balance()}.")

                  elif choice=='5':    
                      print(self.account.get_account_info())

                  elif choice=='6':   
                      print("exiting ATM. Have a great day!")
                      break
                   else:
                      print("Invalid choice. Please try again.")

          account = BankAccount("Alice","123456",1000)
          atm=ATM(account)
          atm.run()
                      
                
                
