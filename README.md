Create dataset_20200616
Dataset of clients eligible for an opening campaign for an instalment product in Poland. Aim is to choose clients with lower risk, propose higher daily limits which are currently rather low and create subset of clients eligible for cash product.

The code should generate around 4.5k (data valid to June 16th 2020).

The whole analysis is based on these files from Verca Charvatova: doc

Here is a brief description of the method for choosing clients:

+ clients have to be registered in Twisto
+ age between 21 and 67
+ if client has Twisto Free account he has to have it for at least 120 days, if she has Twisto Credit, there is no time condition
+ client has at most 1 rejection of Twisto registration
+ no default in 6 and 11 months
+ paid at least one invoice
+ more than 1 month after registration
+ limit was not decreased in history
+ desired limit at time of application was not higher then current limit
+ income at least 1.000 PLN
+ payment capacity at least 200 PLN
+ Nikita score higher than 364 (excluding last 3 deciles od score)
+ historical DPD <= 5
+ current DPD = 0
+ excluding clients with at least 1 invoice which is currently deffered for more than twice
+ no frauds and black lists
+ calculated instalment limit at least 170 PLN
+ no deferral clients (we will target them with other campaigns)

Other calculations
+ new daily limit is a function of current daily limit and score
+ payment capacity is inspired by new Czech payment capacity model (simplier than CZ and also works with CZ constants - PL has to be developed later)
+ maximal monthly repayment is a function of payments capacity and income
+ instalment limit as function of daily limit, payment capacity and income
