# hothur.arbaz
class ATM:
  # Assuming __init__ would be here or defined elsewhere.
  # This code snippet assumes it's part of an ATM class definition.

  def menu(self):
    print('''
    1) Press 1 to Create Pin.
    2) Press 2 to Cash Withdrawl.
    3) Press 3 to Cash Deposite.
    4) Press 4 to Cash Transfer.
    5) Press 5 to Check Balance.
    6) Press 6 to Exit.
    ''' )
    user_choice = input("Please Enter your Choice:")

    if user_choice == '1':
      self.create_pin()

    elif user_choice == '2': # Corrected variable name
      self.withdraw()
    # Add other conditions as needed for other menu options

  def create_pin(self):
    ask1 = input('enter the pin.')
    self.pin = ask1 # Corrected assignment and variable

    user_balance = int(input("enter balance"))
    self.balance = user_balance

    print("pin created successfully")
    self.menu()

  def withdraw(self):
    ask2 = input("enter your pin")
    if ask2 == self.pin:
      amount = int(input("enter the amount"))

      if amount > self.balance:
        print("insufficient balance")

      else:
        self.balance -= amount # Update balance
        print(f"Withdrawal successful. Remaining balance: {self.balance}")
    else:
      print("Incorrect PIN.")
    self.menu() # Return to menu after withdrawal attempt
