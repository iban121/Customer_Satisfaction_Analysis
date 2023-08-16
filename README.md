# Happy Customers 

## Overview 

The client is a startup in the logistics and delivery domain, making on-demand deliveries to their customers. They recently surveyed a select customer cohort asking them to label 0 or 1 for six different areas:

X1 = My order was delivered on time
X2 = Contents of my order was as I expected
X3 = I ordered everything I wanted to order
X4 = I paid a good price for my order
X5 = I am satisfied with my courier
X6 = The app makes ordering easy for me

And, the customers rated the company on a scale of 1-5, where 5 indicates the highest satisfaction. 

## Data Wrangling and EDA

There were no missing data, and all the labels were classified as integers from 1-5. 

## ML Model

## Best model

## Conclusions
The most important features: X1 and X5
Accuracy of final model: 86.5%

Whilst the stacked model reached an accuracy of 86.5%, and therefore, meets the success criteria, I would recommend that the area under the Receiver Operating Characteristic Curve is a better metric. This is because the AUC examines a model's performance over varying threshold values. In this case, as we only have 126 data points, and with an 80:20 split of training and testing datasets, we have only 26 data points in the dataset. This means an incorrect prediction in the very small testing set will be penalised quite heavily. I noticed this as the accuracy scores, even with hypertuned parameters hovered around 69%. The advantage of using the AUC as the metric of choice is I would recommend we use the hypertuned support vector classifier model, as this has the highest AUC and is a far simpler model than the stacked model. 

### Improvements to the Survey
There were no missing data in the dataset which is quite spurious. It would be interesting to know how many people didn't reply to the survey- sometimes a lack of reply can be quite useful as well. 

With this in mind, we can see for X1: 'My order was delivered on time' there are no ratings of 1 for happy customers, and neither happy nor unsatisfied customers voted for a rating of 2. This could mean that the delivery time is relatively great, but it could mean there's not enough representation of each type of customer. For example, maybe there are unhappy customers who aren't actually filling out the survey and are also stopping the use of services. In order to determine this, we need to look at how many customers are recurrent users, and what their responses were versus customers who stopped using the company's services. In addition, another important feature that was identified is X6: 'The app makes ordering easy for me'. It's noteworthy that a large proportion of unhappy customers gave this a rating of 3 whilst happy customers did mostly give this feature high ratings. So, additional information would be useful to address the problems unhappy customers are facing. One possible piece of information could be the devices/operating systems the users are opening the app on- this could help identify if there are specific OS users that are facing problems or not. 

Furthermore, there are quite a few customers, both happy and unhappy customers, who were disappointed with the contents of their order. However, the vagueness of the question means we don't know what they were actually unhappy with. Was it the actual products or the products didn't match what they were advertised to be on the app? In order to gain a deeper understanding of this issue, the types of products information about the products would be useful. 


