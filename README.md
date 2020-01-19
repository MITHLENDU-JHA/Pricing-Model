# Pricing-Model
Multiple resgression model

								
								
Regression Statistics							
Multiple R	0.964867746							
R Square	0.930969768							
Adjusted R Square	0.915629717							
Standard Error	55.32456193							
Observations	23							
								
ANOVA								
 	df	SS	MS	F	Significance F			
Regression	4	743027.2104	185756.8	60.68882924	3.33809E-10			
Residual	18	55094.52874	3060.807					
Total	22	798121.7391	 	 	 			
								
 	Coefficients	Standard Error	t Stat	P-value	Lower 95%	Upper 95%	Lower 95.0%	Upper 95.0%
Intercept	90.8615058	35.79076373	2.538686	0.020580592	15.66790145	166.0551102	15.66790145	166.0551102
Screen	144.9641763	17.35894383	8.350979	1.32254E-07	108.4943886	181.433964	108.4943886	181.433964
Capacity	73.77041469	11.36572055	6.490606	4.192E-06	49.89192187	97.6489075	49.89192187	97.6489075
Connectivity	126.7642873	23.43831941	5.408421	3.86917E-05	77.52220544	176.0063691	77.52220544	176.0063691
Gen 	62.15581502	28.43913985	2.185573	0.042306164	2.407399308	121.9042307	2.407399308	121.9042307


Analysis:-
Multiple R: -  here multiple R talks about the correlation between two variable that means here price is 96% depend on rest all independent variable
R Square:- here higher (93%) R Square values represent smaller differences between the observed data and the fitted values. Here 93% R Square is showing The data point is very close to regression line that means a very low noise in the data which seems fantastic.
Adjusted R Square:-  here Adjusted R-square is 91% which indicates that there are new terms improving in the model that means here overspecified model is more likely to reduce the precision of coefficient estimates and predicted values. You don’t want to include more terms in the model then necessary.
Standard Error:- Here standard error is 55% that indicates here prediction is quite more that means the model is having more dust which is estimation if standard error will be less than it will indicate that model is good(less dust is there).


Sum of square:- sum of square talks about the distance between each data point and the line of best fit is squared and then summed up.
So here the distance between actual and predictable values is 743027 which result indicates
A large degree of variability within the data set.

Mean square :- Here mean square is obtained by dividing the term sum of square by the degree of freedom.
So here treatment mean square, it indicates represent the variation is 185756 between the sample means.



Codded data:-
Price	Screen	Capacity	Connectivity	Gen 
279	1	1	0	0
379	1	2	0	0
399	1	1	0	1
399	2	1	0	0
409	1	1	0	0
499	1	3	0	1
499	2	2	0	0
499	2	1	0	1
529	1	1	1	1
529	2	1	1	0
599	1	4	0	1
599	2	3	0	1
609	1	2	1	0
629	1	3	1	1
629	2	2	1	0
629	2	1	1	1
699	2	4	0	1
729	1	4	1	1
729	2	3	1	1
799	3	2	0	1
829	2	4	1	1
949	3	4	0	1
1079	3	4	1	1

Question solve in python:-
Q1- Design the product with all advanced fetures and predict the price?
data = [['3','4','1','1']]
df2 = pd.DataFrame(data, columns = ['Screen','Capacity', 'Connectivity', 'Gen'])
df2
output:-
	Screen	Capacity	Connectivity	Gen
	3	4	1	1

df2_pred = reg.predict(df2)
print(df2_pred)
output:- [1009.75579572]
so if you take high all advanced features [3,4,1,1] price will be Rs.1009

Q2- Design another product with chepeast price possible?
print(df.min())
output:-
Screen	Capacity	Connectivity	Gen
   1                1                 0                  0
Price 279
Q3- if for the target price is the $400 what best product can be design? List the features.
df_out[df_out['Pred_Price'] < 400]
output:-
Screen	Capacity	Connectivity	Gen
     1             2                  1                  0
