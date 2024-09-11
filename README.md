# Position_Sizing_Calculator
# It is a position sizing calculator for Trading Enthusiasts  to Manage their Risks and Minimize their Losses. 🤑
# Position Sizing Calculator
account_size = float(input("Enter the account size: "))


def risk_A(risk_amount):
    return risk_amount


def risk_P(risk_percentage):
    risk_amount2 = account_size * (risk_percentage / 100)
    return risk_amount2


risk_type = input("Do you want to enter the AMOUNT you want to risk or the PERCENTAGE \n"
                  "Type a for AMOUNT \n"
                  "Type p for PERCENTAGE\n"
                  "")
if risk_type == "p":
    risk = float(input("Enter the percentage: "))
    risk_2 = risk_P(risk)
elif risk_type == "a":
    risk = float(input("Enter the amount: "))
    risk_2 = risk_A(risk)
else:
    print("INVALID INPUT")

stopLoss_level = float(input("Enter you stoploss level: "))
entry_level = float(input("Enter you entry level: "))
difference = stopLoss_level - entry_level

# Final Calculation
formula = risk_2 / difference
if formula < 0:
    formula = formula * -1
print(f'{formula} is the quantity you need to trade')
