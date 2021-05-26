# IMD-shapley
## research direction
The English Indices of Deprivation 2019 contains 7 domains of deprivation, which are combined using non-linear relationship to create the Index of Multiple Deprivation. 
This research aims to study how these indices contribute to the individual and overall values of IMD. Potential methods include Shapley values and SHAP (Shapley Additive exPlanations), which stem from game theory and have been used to explain individual predictions in machine learning. 


Q1：Do Individual IMD means deprivation of 7 domains? Since there is only a column in the data about IMD. If individual IMD means that, the research direction could be separate to two parts: 1.how the data in sub domains contribute to the individual domain and 2.how these 7 domains contribute to the overall IMD?

(Technique report p82)
The **Income Deprivation Domain and Employment Deprivation** Domain are constructed as simple rates of the population at-risk. Separate indicators in these domains are constructed as non-overlapping counts and are simply summed together to identify the total at-risk population for the domain. 
so we do not need to calculate how indicators contribute to these domain.


In the other domains the indicators are on different metrics and therefore it is not possible to calculate a simple rate. The indicators are **standardised by ranking and transforming to a standard normal distribution based on their ranks**, before combining with selected weights to form the domain score: 
• In three domains – the Children and Young People sub-domain of the Education, Skills and Training Deprivation Domain, the Health Deprivation and Disability Domain, and the Crime Domain – maximum likelihood factor analysis is used to generate appropriate weights for combining the standardised indicators into a single score per domain, or sub-domain. Maximum Likelihood factor analysis is used to determine what weight to give each of these indicators when combining them. It does this by testing the extent to which each of the indicators measure the underlying aspect of deprivation20. Factor analysis is described in Appendix E.  (Technique report p82)
• In the remaining two domains, equal weights have been applied. 

transformed data can be found in "File 9  Transformed domain scores"
![image](https://user-images.githubusercontent.com/71642902/119590957-516c4d00-be08-11eb-81d1-75c8bc13ca73.png)

Q2：There are specific weight for each domain, what we need to do is to skip step 3,4,5,6 and use indicators in 2 to calculate IMD in 7?
(Technique report p21-22)
The exponentially transformed domain scores are combined using appropriate domain weights to form an overall Index of Multiple Deprivation
![流程图](https://user-images.githubusercontent.com/71642902/119592065-60ec9580-be0a-11eb-8bb1-b0fd70f4ae99.png)
The weights employed in the construction of the Index of Multiple Deprivation 2019 are shown in the table below. These weights are unchanged since the construction of the Index of Multiple Deprivation 2004 when the Crime Domain was introduced, and the seven current domains established. 
Table 3.1. Domain weights used to construct the Index of Multiple Deprivation 2019 
Domain 	Domain weight (%) 
Income Deprivation Domain 	22.5 
Employment Deprivation Domain 	22.5 
Health Deprivation and Disability Domain 	13.5 
Education, Skills and Training Deprivation Domain 	13.5 
Barriers to Housing and Services Domain 	9.3 
Crime Domain 	9.3 
Living Environment Deprivation Domain 	9.3 
we will not need these weight?

Q3: If the answer for Q2 is Yes, then what method do you recommend to use, like deep learning?

Q3:There are total 39 dataset needed, but only about 20 is publiced. Using these indicators (and machine learning method) to fit the IMD and then calculate their shapley value to explain the prediction. Would the result be baised?  By the way, how much accuracy do you think is acceptable in the machine learning process?

## Literature Review
Young (1985) axiomatizes the Shapley value with three axioms: Efficiency (Pareto optimality PO), Equal Treatment Property (Symmetry), and Marginality.  
 
Index of Multiple Deprivation (IMD) for different countries may consist of different indicators, but the main domain for them is always the same, as Income; Employment; Health; Education; Geographical Access; Crime; and Living Environment (such as IMD for New Zealand and England) (Exeter et al., 2017). 

The IMD using expert judgement to allocate weights to different dimensions. Since it all depends on the experts’ experience and considerations, this method always raises concerns about paternalism. There are other methods such as correlation-based weights which are based on the data and the correlation between different dimensions of the deprivation. This method uses PCA or FA as the calculation functions. It cannot be used when we need to summarise several measures into a single measure, instead of doing the dimension reduction to construct a single useful measurement (Watson et al., 2054).

## Reference
Exeter, D. J., Zhao, J., Crengle, S., Lee, A. and Browne, M. (2017). ‘The New Zealand Indices of Multiple Deprivation (IMD): A new suite of indicators for social and health research in Aotearoa, New Zealand’. PLoS ONE. Public Library of Science, 12 (8), pp. e0181260–e0181260. doi: 10.1371/journal.pone.0181260.


Watson, V., Dibben, C., Cox, · Matt, Atherton, I., Sutton, M. and Ryan, M. (2054). ‘Testing the Expert Based Weights Used in the UK’s Index of Multiple Deprivation (IMD) Against Three Preference-Based Methods’. Social Indicators Research, 144, pp. 1055–1074. doi: 10.1007/s11205-018-02054-z.


Young, H. P. (1985). ‘Monotonic solutions of cooperative games’. International Journal of Game Theory. Physica-Verlag, 14 (2), pp. 65–72. doi: 10.1007/BF01769885.


