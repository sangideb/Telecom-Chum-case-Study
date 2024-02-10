# Telecom-Chum-case-Study


Telecom Churn Case Study

Problem statement

In the phone company world, people can easily switch to a different phone service. The phone industry faces a problem where 15-25% of customers leave each year. It's way more expensive to get new customers than to keep the ones they already have. So, keeping customers is now more important than getting new ones.
Big phone companies really want to keep their high-paying customers.
To stop customers from leaving, phone companies want to figure out who might leave before it happens.
This project looks at data from a top phone company. We're going to study this data and make models that can tell us which customers might leave. We also want to know what things show us that a customer might leave.


Let us understand Churn

In the phone world, there are two main ways people pay for services: postpaid (paying a bill after using the service) and prepaid (paying or recharging with a set amount before using the service).
With postpaid, if someone wants to leave, they usually tell the company, and you know they've left. But with prepaid, people can just stop using the service without saying anything. It's hard to know if they left for good or just temporarily stopped using it, like when someone travels abroad.
Predicting who might stop using the service (churn) is more challenging for prepaid customers. This is a big deal in places like India and Southeast Asia where prepaid is common, compared to Europe and North America where postpaid is more popular. This project focuses on the Indian and Southeast Asian market.



Definitions of churn
There are various ways to define churn, such as:
Revenue-based churn: Customers who have not utilised any revenue-generating facilities such as mobile internet, outgoing calls, SMS etc. over a given period of time. One could also use aggregate metrics such as ‘customers who have generated less than INR 4 per month in total/average/median revenue’.
The main shortcoming of this definition is that there are customers who only receive calls/SMSes from their wage-earning counterparts, i.e. they don’t generate revenue but use the services. For example, many users in rural areas only receive calls from their wage-earning siblings in urban areas.
Usage-based churn: Customers who have not done any usage, either incoming or outgoing - in terms of calls, internet etc. over a period of time.
A potential shortcoming of this definition is that when the customer has stopped using the services for a while, it may be too late to take any corrective actions to retain them. For e.g., if you define churn based on a ‘two-months zero usage’ period, predicting churn could be useless since by that time the customer would have already switched to another operator.
In this project, we will use the usage-based definition to define churn.


High Value Churn
In India and Southeast Asia, around 80% of the money phone companies make comes from the top 20% of customers, who are considered high-value customers. So, if we can stop these high-value customers from leaving, we can avoid losing a lot of money.
In this project, we'll figure out who the high-value customers are based on a specific measure (explained later), and we'll only focus on predicting if these valuable customers might leave.

Understanding the business objective and the data
The dataset includes details about customers over four months: June, July, August, and September, labeled as 6, 7, 8, and 9. The main goal is to forecast whether customers will leave in the last month (September) by analyzing information from the first three months (June, July, August). Knowing how customers usually behave when they decide to leave will be useful for doing this task effectively.

Understanding customer behaviour during churn
Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle :
•	The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.
•	The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.)
•	The ‘churn’ phase: In this phase, the customer is said to have churned. You define churn based on this phase. Also, it is important to note that at the time of prediction (i.e. the action months), this data is not available to you for prediction. Thus, after tagging churn as 1/0 based on this phase, you discard all data corresponding to this phase.
In this case, since you are working over a four-month window, the first two months are the ‘good’ phase, the third month is the ‘action’ phase, while the fourth month is the ‘churn’ phase.

