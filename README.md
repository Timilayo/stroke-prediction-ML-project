# stroke-prediction-ML-project

Please note: Kindly find the link to the google doc for the neccesary images for each of the steps discussed (https://docs.google.com/document/d/1dv0erZmwfsp_nS4jl-bVN_5v_pbfoGKezaL7AjpnCRA/edit?usp=sharing)

This project involves predicting whether a patient will have a heart stroke or not based on his/her comorbidities, work, and lifestyle.

# Background
Stroke is a disease that affects the arteries leading to and within the brain. It occurs when a blood vessel that carries oxygen and nutrients to the brain is either blocked by a clot or bursts (or ruptures). When that happens, part of the brain cannot get the blood (and oxygen) it needs, so it and its brain cells die. 

Risk factors
Have overweight or obesity
Age, 55 years of age or older
Have a personal or family history of stroke
Have high blood pressure
Have diabetes
Have high cholesterol
Have heart disease, carotid artery disease, or another vascular disease
Having a sedentary lifestyle (often sitting or lying down while engaged in an activity like socializing, watching TV, playing video games, reading, or using a mobile phone or computer for much of the day)
Consume alcohol excessively, smoke, and use illicit drugs

# Steps
Import the necessary libraries

 
# Read the data to display the columns and data on each.

Check the information about the data, to check for how many null(Null values in the dataset are the empty field) values and do any cleaning necessary. Those null values must be filled with another meaningful value or they must be dropped from the dataset so that the machine learning model can perform well.


#All other columns had complete values except bmi. Bmi happens to be very important in predicting stroke as seen from the background. Bmi is simply the body mass index and gives information about the measure of body fat based on height and weight. Bmi had 201 missing values out of 5110 rows.
I decided to use a boxplot to find out which is a better measure of the central tendency of data and use that value for replacing missing values appropriately in the ‘bmi’ data. 

#The black spots above the Ist quartile (around 50 on the y-axis) show the data is skewed. There are several or large numbers of data points that act as outliers (The black spots above the Ist quartile (around 50 on the y-axis). Outliers data points will have a significant impact on the mean and hence, in such cases, it is not recommended to use the mean for replacing the missing values. Using mean values for replacing missing values may not create a great model and hence gets ruled out, so I used median instead.



#Replaced the missing values in bmi with median. And we can see that all the column are filled with the same amount of data and no missing values in bmi agin.

#I decided to check more information about the datasets. From this information, I can understand the dispersion of the data and how much exploratory data analysis would be needed to make the data fit enough for the machine to learn without creating any disparity and for more efficient machine learning. For Age, the Min is 0.08yrs while the maximum is 82years and the median is 45 years, this gives me information that the ages collected have a normal distribution (the middle age is almost half of 82) while skewness of data is observed in bmi and average glucose level (Max = 271, Min = 55, Avg= 91 & Max = 97, Min = 10, Avg = 28 respectively)


#I dropped the ID column because it’s not useful for the analysis or to train the machine. Leaving it can cause more disparity in the efficiency of the result.


#Checking for outliers, as in No 6, outliers were observed in bmi and average blood glucose. The same trend observed in the histogram 


#Univariate analysis for categorical variables - value counts show the unique values and the number of times they occur in the data sets. For Gender, there is almost an equal spread of the data between females and males, however, that is not the same for Hypertension and heart diseases. This can affect our training as the machine can learn the wrong trend to give ineffective output.

Here is the scenario for better understanding:
I’m trying to work on a machine that can predict if a person will have a stroke or not. I'll have to train the machine with previous data so that it can learn the trends and then use this trend for future features that it will use to predict if a person will have a stroke or not. As discussed in the introduction, risk factors for stroke include BMI, hypertension etc hence the need for the important features in the data provided to have at least a normal distribution to avoid any bias while training the machine.


# Feature selection: 
This is the process of reducing the number of input variables when developing a predictive model to improve the performance of the model. I used the embedded methods since I’m working on large datasets. According to the picture below: the higher the score, the higher the correlation of the feature in relation to the output variable (stroke), and the more important the input variable training the model
 

#Finally, I compared different machine learning models to use for the prediction.


# References
About Stroke. American Stroke Association. Available at: https://www.stroke.org/en/about-stroke#:~:text=Stroke%20is%20a%20disease%20that,or%20bursts%20(or%20ruptures)

How to Handle Null Values in Pandas. Available at:
https://pythonsansar.com/how-to-handle-null-values-in-pandas/

Kumar, A. (2021). Python – Replace Missing Values with Mean, Median & Mode. Available at:
https://vitalflux.com/pandas-impute-missing-values-mean-median-mode/


