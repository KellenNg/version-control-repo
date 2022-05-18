# Parent Class
class User:
    def __init__(self, name, age, gender):
        self.name = name
        self.age = age
        self.gender = gender

    def show_details(self):
        print("Personal details")
        print("")
        print("Name:", self.name)
        print("Age:", self.age)
        print("Gender:", self.gender)


Kellen = User("Kellen", 21, "Male")
Kellen.show_details()


# Child Class
class Bank(User):
    def __init__(self, name, age, gender):
        super(). __init__(name, age, gender)
        self.balance = 0

    def deposit(self, amount):
        self.amount = amount
        self.balance = self.balance + self.amount
        print("Account balance has been updated : $", self.balance)

    def withdraw(self, amount):
        self.amount = amount
        if self.amount > self.balance:
            print("Insufficient Funds. Balance Available : $", self.balance)
        else:
            self.balance = self.balance - self.amount
            print("Account balance has been updated : $", self.balance)

    def view_balance(self):
        self.show_details()
        print("Account balance has been updated : $", self.balance)


Kellen = Bank("Kellen", 21, "Male")
print("")
Kellen.deposit(1000)
print("")
Kellen.withdraw(500)
print("")
Kellen.view_balance()
# 如果前面有加print, eg. print(Kellen.view_balance()), 就会显示出return value, eg."None".应该要纯object.method()