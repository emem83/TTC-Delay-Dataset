This project focused on cleaning and analyzing TTC subway delay data to uncover patterns and insights into service disruptions.

📊 Key Activities:

**Data Cleaning & Preprocessing**: 
The data set spans from January 1, 2014 to September 30, 2024 with 215,602 rows of data. I also merged the delay dataset with the TTC delay codes which came in a separate excel file and which the TTC have two (2): one for Lines 1, 2, and 4 and the other for Line 3.

It's not the cleanest of datasets as it has 56,167 null values and a lot of typographical errors, particularly in the Station attribute. I populated missing values by extrapolating information from other attributes like Line. For values that I could not extrapolate, I removed the entire row from the dataset or tagged it as Other. I corrected spelling errors by using a dictionary of key words for the Station names. 

Another issue with the data set is the tagging of delay occurrences. There are numerous entries whose Station was tagged as 'X station approaching X station', or in some other form. To simplify the analysis, I assumed that these delay occurrences happened at the source of the train and not the destination. 

The Min Delay attibute which represents the number of minutes of the delay is undervalued because the TTC rounds down the duration of delays to the nearest minute. Anything that lasts less than a minute is valued at '0', even if the actual delay duration lasted for 59 seconds. 

One of the goals of this project is to recommend solutions to delay causes. The TTC identified more than 100 delay causes in the data set. To simplify recommendations, I grouped the delay causes into five (5) categories: Passenger Related, Equipment Related, Personnel Related, Fortuitous Events, and Undefined. 

**Exploratory Data Analysis (EDA)**: 
I identified key trends in delay frequency, duration, and common causes using visualizations and statistical analysis (linear regression to determine which delay causes have statistically significantly worsened over time). Focus was drawn on statistically significant delay causes under the Passenger Related, Equipment Related, and Personnel Related Categories. Interestingly, some top delay causes in terms of total delay duration from 2014 to 2024 was found to not be statistically significant. The nature of this delay causes may be that they were time-bound TTC projects that severely impacted TTC operations in the past but has since been resolved or finished.

Exploratory data analysis was also conducted on the Stations.

I created charts and graphs to highlight peak delay periods, station-specific disruptions, and seasonal trends.

🔍 Tech Stack: Python, Pandas, NumPy, Matplotlib, Geopandas, Scipy

* TTC dataset pulled from https://open.toronto.ca/dataset/ttc-subway-delay-data/ 
