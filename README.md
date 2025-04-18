# PwC-Switzerland-Power-BI-Customer-Retention-Dashboard
The organization wants to know which consumers ae likely to churn. In this Dashboard, we develop KPIs based on demographics, businesses service, and customer profiling in order to identify which customers are most likely to churn. The analysis highlights several crucial findingd that should help the board member with coming to future decisions to reduce the churn and promote client loyalty.

# Background information on task:
A few weeks after presenting your dashboard to the management, the Retention Manager from the telecom reaches out to you directly. 
He was impressed by your work and asked if you could put together a dashboard about customer retention.

In addition, to better understand the data, the telecom Retention Manager has scheduled a meeting with the engagement partner at PwC to cover these points:

   1] Customers in the telecom industry are hard-earned: we don’t want to lose them
   2] The retention department is here to get customers back in case of termination 
   3] Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be better to know in advance who is at risk 
   4] We  have done customer analysis with Excel: but it has always ended in a dead-end
   5] We would like to know more about our customers: visualized clearly so that it’s self-explanatory for our management

The Retentions Manager has provided some information, have a look through the resource section.

# Task:
Your colleague, the engagement partner, asks you to do the following tasks:-

   1] Define proper KPIs
   2] Create a dashboard for the retention manager reflecting the KPIs
   3] Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed

The below is the mail from client:
![image](https://github.com/user-attachments/assets/77fd6ff5-23a5-4bd5-9cd9-40a7ddaac69a)

DAX commands used:
Active Customers = COUNTROWS(filter('01 Churn-Dataset','01 Churn-Dataset'[Churn] = "NO"))

Churned Customers = countrows(filter('01 Churn-Dataset','01 Churn-Dataset'[Churn] = "YES"))

DeviceProtection_Percentage = 
VAR TotalCustomers = COUNT('01 Churn-Dataset'[customerID])
VAR DeviceProtection_Yes = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[DeviceProtection] = "Yes")
RETURN DIVIDE(DeviceProtection_Yes, TotalCustomers, 0)

OnlineBackup_Percentage = 
VAR TotalCustomers = COUNT('01 Churn-Dataset'[customerID])
VAR OnlineBackup_Yes = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[OnlineBackup] = "Yes")
RETURN DIVIDE(OnlineBackup_Yes, TotalCustomers, 0)

OnlineSecurity_Percentage = 
VAR TotalCustomers = COUNT('01 Churn-Dataset'[customerID])
VAR OnlineSecurity_Yes = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[OnlineSecurity] = "Yes")
RETURN DIVIDE(OnlineSecurity_Yes, TotalCustomers, 0)

Partner Percentage = 
VAR TotalCustomers = COUNT('01 Churn-Dataset'[customerID])
VAR PartnerCustomers = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[Partner] = "Yes")
RETURN 
DIVIDE(PartnerCustomers, TotalCustomers, 0)

Partner_Active = countrows(filter('01 Churn-Dataset','01 Churn-Dataset'[Partner] = "YES"))

StreamingMovies_Percentage = 
VAR TotalCustomers = COUNT('01 Churn-Dataset'[customerID])
VAR StreamingMovies_Yes = CALCULATE(COUNT('01 Churn-Dataset'[customerID]), '01 Churn-Dataset'[StreamingMovies] = "Yes")
RETURN DIVIDE(StreamingMovies_Yes, TotalCustomers, 0)



