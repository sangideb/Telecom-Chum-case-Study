# Telecom-Chum-case-Study


## Problem statement

In the phone company world, people can easily switch to a different phone service. The phone industry faces a problem where 15-25% of customers leave each year. It's way more expensive to get new customers than to keep the ones they already have. So, keeping customers is now more important than getting new ones.
Big phone companies really want to keep their high-paying customers.
To stop customers from leaving, phone companies want to figure out who might leave before it happens.
This project looks at data from a top phone company. We're going to study this data and make models that can tell us which customers might leave. We also want to know what things show us that a customer might leave.


## Let us understand Churn

In the phone world, there are two main ways people pay for services: postpaid (paying a bill after using the service) and prepaid (paying or recharging with a set amount before using the service).
With postpaid, if someone wants to leave, they usually tell the company, and you know they've left. But with prepaid, people can just stop using the service without saying anything. It's hard to know if they left for good or just temporarily stopped using it, like when someone travels abroad.
Predicting who might stop using the service (churn) is more challenging for prepaid customers. This is a big deal in places like India and Southeast Asia where prepaid is common, compared to Europe and North America where postpaid is more popular. This project focuses on the Indian and Southeast Asian market.

## Understanding the business objective and the data
The dataset includes details about customers over four months: June, July, August, and September, labeled as 6, 7, 8, and 9. The main goal is to forecast whether customers will leave in the last month (September) by analyzing information from the first three months (June, July, August). Knowing how customers usually behave when they decide to leave will be useful for doing this task effectively.

## Understanding customer behaviour during churn
Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle :

•	The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.

•	The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.)

•	The ‘churn’ phase: In this phase, the customer is said to have churned. You define churn based on this phase. Also, it is important to note that at the time of prediction (i.e. the action months), this data is not available to you for prediction. Thus, after tagging churn as 1/0 based on this phase, you discard all data corresponding to this phase.
In this case, since you are working over a four-month window, the first two months are the ‘good’ phase, the third month is the ‘action’ phase, while the fourth month is the ‘churn’ phase.


## Analysis Objective

•	The telecommunications industry typically faces an annual churn rate of 15-25%. Given that acquiring new customers is significantly more expensive than retaining existing ones, customer retention has become a critical focus.

•	In this case study, we analyze four months of customer usage data from a leading telecom firm. The goal is to build predictive models that can identify customers at high risk of churn and determine the main indicators of churn. We specifically consider usage-based churn, where customers with zero usage (incoming or outgoing calls, internet, etc.) over a period are flagged for potential churn. 

•	The study concentrates on high-value customers, as approximately 80% of revenue in the Indian and Southeast Asian markets comes from this segment. Reducing churn among high-value customers can significantly mitigate revenue loss.

•	The dataset spans four consecutive months, from June (month 6) to September (month 9). The business objective is to predict churn in the ninth month using data from the preceding three months.

•	This problem is framed as a classification task, where the objective is to predict whether a customer is likely to churn or not. We explore various modeling techniques including Baseline Logistic Regression, Logistic Regression with Principal Component Analysis (PCA), PCA combined with Random Forest, and Hyper – parameter tuning for the random forest


## Based on the analysis, the strongest indicators of churn are as follows:
1. Customers who churn exhibit significantly lower average monthly local incoming calls from fixed lines during the action period, by 1.27 standard deviations compared to non-churn customers, holding all other factors constant. This stands out as the most influential indicator of churn.

2. Churning customers tend to have a lower number of recharges during the action period, showing a deviation of 1.20 standard deviations compared to non-churners, when controlling for other variables. This emerges as the second strongest predictor of churn.

3. Additionally, churners typically perform recharges of a higher value by 0.6 standard deviations compared to non-churners. When considered alongside the aforementioned factors, this attribute serves as a noteworthy churn indicator.

4. Customers who churn are more inclined to utilize the 'monthly 2g package-0 / monthly 3g package-0' during the action period, with a deviation of approximately 0.3 standard deviations higher than other package types, when other factors are taken into account.




## Based on the identified indicators, the following recommendations are proposed for the telecom company:
1. Focus on customers who exhibit significantly lower than average incoming calls from fixed lines, with a deviation of 1.27 standard deviations below the mean. These users are at the highest risk of churning and should be targeted for retention efforts.

2. Pay close attention to customers who recharge fewer times during the eighth month, with a deviation of less than 1.2 standard deviations compared to the average. This group represents the second highest likelihood of churning and should be prioritized for retention strategies.

3. Prioritize models with high sensitivity for predicting churn. Utilize the PCA + Logistic Regression model, which demonstrates an ROC score of 0.87 and a test sensitivity of 100%. This model is highly effective in identifying customers at risk of churn and can guide proactive retention measures.
![image](https://github.com/sangideb/Telecom-Chum-case-Study/assets/157450757/df52ea07-8534-4815-abb7-1abfb7fa5ec9)





