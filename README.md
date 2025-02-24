# First-studies-
Criar um plano por meio dos estudos da DIO
class ATM:
    def __init__(self, balance):
        self.balance = balance

    def display_balance(self):
        print(f"Current balance: ${self.balance:.2f}")

    def withdraw(self, amount):
        if amount <= 0:
            print("Withdrawal amount must be greater than zero.")
            return

        if amount > self.balance:
            print("Insufficient funds for this withdrawal.")
            return

        self.balance -= amount
        print(f"Withdrawal successful! You have withdrawn: ${amount:.2f}")
        self.display_balance()

# Example usage
def main():
    # Initialize ATM with a starting balance
    atm = ATM(balance=1000.00)

    # Display current balance
    atm.display_balance()

    # Simulate a withdrawal
    try:
        amount_to_withdraw = float(input("Enter the amount to withdraw: $"))
        atm.withdraw(amount_to_withdraw)
    except ValueError:
        print("Invalid input. Please enter a numeric value.")

if __name__ == "__main__":
    main()
