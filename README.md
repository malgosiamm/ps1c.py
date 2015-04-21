# Problem Set 3 
# Name: Małgorzata Metryka
# Collaborators: Natalia Prósińska
# Time Spent: 4h

Initialbal = float(input("What is your outstanding balance on your credit card: "))
interestrate = float(input("What is your annual percentage rate (as a decimal, i.e. 18% is .18): "))

bal = Initialbal
lowpay = bal/12
highpay = (bal*(1+(interestrate/12))**12)/12

while True:
   bal = Initialbal
   monthlypay = (lowpay + highpay)/2

   for month in range(1,13):
       interest = round(bal*interestrate/12, 2)
       bal += interest - monthlypay
       if bal <= 0:
           break

   if (highpay - lowpay < 0.003):

       print ("RESULT")

       monthlypay = round(monthlypay + 0.002999, 2)
       print ("Monthly payment to pay off debt in 1 year: $", round(monthlypay,2))

       bal = Initialbal
       for month in range(1,13):
           interest = round(bal*interestrate/12, 2)
           bal += interest - monthlypay
           if bal <= 0:
               break
       print ("Number of months needed:", month)
       print ("Balance: $", round(bal,2))
       break
   elif bal < 0:

       highpay = monthlypay
   else:

       lowpay = monthlypay
