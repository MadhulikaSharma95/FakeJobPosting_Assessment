Abstract
--------
The goal of this project is to develop a classifier that can distinguish between fake and real jobs. The result will be assessed using two alternative models. Since the data contains both numeric and text elements, one model will be applied to the text data and the other to the numeric data. The result will be a hybrid between the two models. The final model will accept any relevant job posting data and produce a result indicating whether the position is authentic or not.

Introduction
------------
Employment scams are on the rise in the current scenario. Many people fall in the trap of these scammers and lose lots of money and sometimes their current job. Knowing how to differentiate legitimate work opportunities from harmful ones is the best way to protect job seekers from such scams. Machine learning algorithms can be used to develop a model for detecting illegitimate jobs. It can be trained on prior real and fake job listings and can reliably recognize a fake job.

Data Description
----------------
After analysis of data, we found that the job description has been posted from different countries in different languages. There are around 17.8K job descriptions in the dataset, with about 800 of them being fraudulent. The data consists of 13 textual information, 1 integer and 4 binary features. Features department and salary range are dropped for the analysis as they mostly contain null values.

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 17880 entries, 0 to 17879
Data columns (total 18 columns):
 #   Column               Non-Null Count  Dtype 
---  ------               --------------  ----- 
 0   job_id               17880 non-null  int64 
 1   title                17880 non-null  object
 2   location             17534 non-null  object
 3   department           6333 non-null   object
 4   salary_range         2868 non-null   object
 5   company_profile      14572 non-null  object
 6   description          17879 non-null  object
 7   requirements         15185 non-null  object
 8   benefits             10670 non-null  object
 9   telecommuting        17880 non-null  int64 
 10  has_company_logo     17880 non-null  int64 
 11  has_questions        17880 non-null  int64 
 12  employment_type      14409 non-null  object
 13  required_experience  10830 non-null  object
 14  required_education   9775 non-null   object
 15  industry             12977 non-null  object
 16  function             11425 non-null  object
 17  fraudulent           17880 non-null  int64 
dtypes: int64(5), object(13)
memory usage: 2.5+ MB

Analysis
--------
Correlation matrix is plotted to explore the numeric and textual features of the dataset. Fake to real Job Ratio is analyzed using the features City, State and fraudulent. Features title, location, company profile, description, requirements, benefits, required experience, required education, industry, and function are combined to examine the difference between real and fake jobs based on character count. Other text-based characteristics are analyzed to see if any crucial links exist.
The dataset is highly unbalanced with 7699 (95% of the jobs) being real and only 353 or 5% of the jobs being fraudulent. A count plot is represented to show the data.

Model
-----
The numerical model helps us to study the relationship between the numerical data with the help of correlation matrix. There are no strong positive or negative correlations between the numeric values in the correlation matrix.

Calculating fake to real job ration based on states and cities to determine out how many fake jobs are available for each real job, employ the formula below:
        𝑠𝑡𝑎𝑡𝑒 & 𝑐𝑖𝑡𝑦|𝑓𝑟𝑎𝑢𝑑𝑙𝑒𝑛𝑡 = 0 
𝑟𝑎𝑡𝑖𝑜 =  ----------------------
        𝑠𝑡𝑎𝑡𝑒 & 𝑐𝑖𝑡𝑦|𝑓𝑟𝑎𝑢𝑑𝑙𝑒𝑛𝑡 = 1
        
The text-based categories are integrated into one category named text to broaden the analysis on text-related fields. Title, location, company profile, description, requirements, benefits, required experience, required education, industry, and function are the fields that are combined. To display the difference between actual and fraudulent jobs, a histogram representing a character count is used. Real jobs have more frequency of the character count than that of the fake jobs.


Result
------
Both the textual and numerical model helped us with better insights to the data by predicting fake jobs up to a certain level with all the details provided for a given job. The most intriguing aspect of this project was discovering how specific regions are the epitome of job fraud. Bakersfield, California, for example, has a 3:1 ratio of fake to actual jobs. This type of environment necessitates further monitoring. Another intriguing aspect was that most entry-level positions appeared to be fake. Scammers appear to prefer to target young people with a bachelor's degree or a high school diploma who are looking for full-time work. Text data preprocessing was the most difficult component. The information was in a specific format. It took a lot of effort to clean it.

Future Scope
------------
The dataset for this research is extremely imbalanced. Most jobs are real, while only a handful are fake. Real jobs are being identified successfully because of this irregularity. A well-balanced dataset should yield better outcomes. Multiple Machine Learning algorithms can be used to predict the accuracy of the models and models can be combined to get the best possible results.

Reference
---------
https://www.kaggle.com/shivamb/real-or-fake-fake-jobposting-prediction
