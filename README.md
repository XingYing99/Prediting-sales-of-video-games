# Data-Visualisations

# 1. Case Study Description
OldKids is a group of avaricious game distributors, and with COVID-19, many people turned to home entertainment such as video games
during a period of lockdown. OldKids wants to maximize its profitability during this golden period but has limited resources to do so. Thus,
OldKids need to be vigilant in only distributing games that will be successful.
OldKids distributes games to emerging markets like Africa, South America, and China. The reason why game developers are not able to
access those markets is due to regulatory issues. Compared to North America and Europe, emerging market regulations are much stricter
(Takahashi, 2020). The cumbersome regulatory approval needed causes a delay in game releases in emerging markets.
With the abundance of games out there, picking one will require a strong understanding of what moves the industry. As such, the key will be
in understanding the factors that contribute to the sales of games which will be the aim of this report. With the elements in hand, OldKids
aims to build a model to predict how a game would sell in those regions. The results will enable OldKids to pick the games to distribute.
# 2. Data Sources
The data used for this report were obtained from kaggle.com.
# 3. Business Questions and Hypotheses
To succeed in the gaming distribution industry, the following questions will be the guide to our approach:
a) Where should the games have exposure to?
- Since games with higher sales are deemed to be more successful, games with exposure to areas with higher pre-existing sales will
have a higher chance of succeeding.
b) How will the console affect the popularity of games?
- It is hypothesized that consumers will stick to games that are available on the consoles they own. Thus, having games on
non-popular consoles will be detrimental to game sales. OldKids can use the popularity of consoles as a data point in determining
the suitability venture.
c) Why do we use other regions as the variable of prediction?
- It is hypothesized that the sale of other regions and sales from the rest of the regions is correlated to some degree. Being able to
predict the sales in other regions will help OldKids decide which games to distribute based on the sales results of the rest of the
regions..
d) Why are the sales of games different in different regions?
- It is hypothesized that each region has its genre preference. Knowing which genre is popular will help with the picking of games to
distribute.
e) Which genre is the most popular
- It is hypothesized that consumers pick games based on their preferred genres. Knowing which genre is popular will help in
narrowing down the scope.
# 4. Data Visualisation & Analysis
To address the business questions mentioned, the data collected was analysed using Python due to its flexibility and repertoire of analytical
tools.
We have decided to analyse different independent variables using different types of data visualisation methods.
![image](https://user-images.githubusercontent.com/71431944/157258226-3d563782-598e-4ea0-b9b7-669ed974693b.png)

4.1 Filtering of Data
We decided to drop the years before the year 2000 because of a few reasons.
![image](https://user-images.githubusercontent.com/71431944/157258298-c7658f3b-02a7-44fe-a40d-ecb2815ffc32.png)
Firstly, the distinctly high average global sales per game before 2000 will distort our investment decision. The high average global sales for
each game before the year 2000, as shown above (Fig A), is due to the lack of game developers. The trivial number of games before the
year 2000 proves a lack of game developers. With the lack of options for consumers, naturally, the consumers will get whatever they can
get their hands on. With a large customer base and a limited number of games, the average sales per game will naturally be sky-high. Thus,
the games that did well in the earlier years may not be a true reflection of what consumers want. If the earlier years' findings are taken into
consideration, our investment decision will be distorted.
Secondly, there is a change in gaming preference over the decades. As shown in Fig B, in the earlier years, games' choice was heavily
concentrated in certain areas. For instance, in 1996, the fighting category was the most popular, and in 1997 it was racing. Moving on to
later years, the preferences for games were spread across multiple genres. The exploration of the reasons for such finding can be attributed
to many factors that will not be explored due to this report's limitation. As such, the years before the year 2000 will be removed to prevent
any investment decision-making error when accounting for gaming preference.
Thirdly, back then, there were fewer alternatives to console games. Mobile phones and computers were not available to the masses before
4
the year 2000. The public only has access to console games. Now, mobile phones and computers are easily attainable, and games can be
played on those devices too. To retain customers from migrating to other devices, console developers deployed numerous strategies. One
of them is acquiring game developers to ensure that the games developed will solely be for consoles and no other devices (Wong, 2019).
The strategies will help in tying consumers down to console gaming. Thus, Including the information from the year before 2000 will hinder
our investment decisions, as the environment now and back then is different.
Hence, our decision to drop the years before 2000 will help us make a better investment decision as the findings after dropping those years
will be more relevant. In turn, will help us better able to pick up on consumers' preferences and the gaming industry's business environmen

4.2 Correlation Plot of Numerical Variables
![image](https://user-images.githubusercontent.com/71431944/157258541-5d0c6eff-7a07-4f48-ae99-586723f2061f.png)
As can be seen from the heatmap above, the correlation between Other_Sales, Global_Sales, NA_Sales and EU_Sales is very high, which
are 0.81,0.73 and 0.72. Therefore, we considered including all of them as independent variables in our regression model to estimate sales
in other regions. However, we found that EU_Sales and NA_Sales also had a high correlation, so we decided to remove EU_Sales from our
regression model to avoid multicollinearity

4.3 Platform/Publisher analysis

We constructed a bar chart by plotting sales against platforms to identify the platforms with high regional and global sales with reference to
Figure D. An analysis of this bar chart shows that PS2 has the highest global sales, followed by X360, PS3, Wii, etc. Besides, the top-selling
platforms in NA, EU, and Japan are X360, PS3, and DS, respectively.
![image](https://user-images.githubusercontent.com/71431944/157258647-e381a304-7283-45a8-a0e0-220f2d8997ea.png)
To select the platform with the highest sales in other regions, we came up with Boxplot (Figure C). The blue lines indicate the 75th
percentile and 25th percentile of sales in other regions for different platforms. The red line indicates the median of the sales. We choose
median instead of mean as the line indicator, this is because the middle lines on the boxplots are the medians of the respective platforms,
allowing us for easier comparison. We can see that at the 75th percentile, Wii, X360, PS3, PS2, PS4, PSP, and XOne’s 75th percentile
Other_Sales are higher than the average 75th percentile line. The PS3 and PS2’s 25th percentile sales are higher than the average 25th
percentile line across the platforms. As for the median, we can see that Wii, X360, PS3, PS2, PS4, WiiU, XOne, and PS’s median
Other_Sales are higher than the average median Other_Sales across all games. After multiple comparisons, we found that Xone, PS4 and
PS3 are the platforms that are more likely to outperform others in terms of achieving high sales in other regions.

Concerning the word cloud in Figure D for different publishers, the word's size is proportional to the number of games released by each
publisher. We observed that words such as “Nintendo” and “EASports” were rather large in size and therefore meant that these platforms
occupy a higher market share. As distributors, we prefer to buy the rights to games from large publishers as these games are likely to be
more popular. According to this word cloud, it is easy to observe the market share of different publishers.
4.4 Genre analysis

![image](https://user-images.githubusercontent.com/71431944/157258835-e0d98f9a-d199-42de-9443-46eb60d4260f.png)
To select the genre with the highest sales in other regions, we used a Boxplot (Figure E). The blue lines indicate the 75th percentile and
25th percentile of sales in other regions for different genres. The red line indicates the median of the sales. We can see that at the 75th
percentile, Sports, Racing, Misc, and Shooter’s 75th percentile are higher than the average Other_Sales 75th percentile. For the 25th
percentile, only Adventure and Strategy’s 25th percentile falls below the average 25th percentile. Thus, as a distributor we are inclined
towards Sports, Racing, Misc and Shooter while avoiding Adventure and Strategy

4.5 Sales analysis

![image](https://user-images.githubusercontent.com/71431944/157258941-caf68487-6d47-4430-9de7-0122bc3d46ff.png)

In Figure F, the blue diagonal line represents the best fit line for Other_Sales against NA_Sales for genres. This best fit line can help to
determine the performance of Other_Sales compared to NA_Sales for each genre. If a genre is plotted below the best fit line, it performs
worse than average across all genres. If a genre is plotted above the best fit line, it is considered to perform better than average across all
genres. From the figure, Action, Sports, Racing, and Shooter are the genres that are above the best fit line. These genres are what
distributors should look out for when choosing which game to purchase the rights to distribute.
Similarly, in Figure G, the blue diagonal is the best fit line. Figure G represents Other_Sales against NA_Sales for platforms. GC, GC, PSP,
PS4, PS2 and PS3 are the platforms that are above the best fit line. These platforms above the best fit line are ideal platforms for games to
achieve better sales in Other_Sales than NA_Sales.

4.6 Rating Analysis
![image](https://user-images.githubusercontent.com/71431944/157259036-b0d5165e-6615-4da2-97b5-27cade107c04.png)
Based on Figure H and I, we can see that most of the genres appear to have similar quantile ranges in the box-plots in terms of critic_score
and user_scores. For instance, we can see that both the interquartile critic score range for racing and platform falls between 60 to 80.
However, we noticed a considerable difference in terms of Other_Sales and NA_Sales shown in figure F. On top of that, we also see that
despite a vast difference in terms of the Other_Sales and NA_Sales for action and shooter, the interquartile user_score for both genres falls
between the same range of 6.5 and 8. By combining these observations, we can see that user score and critic score may not be significant
variables in predicting Other_Sales. We have proven these observations by plotting the correlation plot (Figure J) for these 3 variables. We
can see that the correlation between user_score and Other_Sales is 0.056 and the correlation between critic score and Other_Sales is 0.19
while the correlation between user_score and NA_Sales is 0.08. The correlation between critic score and NA sales is 0.23. These ascertain
our hypothesis that user_score and critic_score is not significant variables in predicting Other_Sales. Therefore, we should not focus too
much on the critic_score and user_score to predict Other_Sales based on these observations.
However, these observations can be further tested statistically by validating our hypothesis in our modelling using the variance importance
score.

![image](https://user-images.githubusercontent.com/71431944/157259115-f7e8df5c-4ebf-40d1-93fc-b56068648827.png)

With reference to figure K, we constructed a heatmap by capturing age data for each game to determine which target age was highest
within each genre and which genre was most popular across all video games. An analysis of this heatmap in a horizontal manner further
shows that the target age varies by genre, such as sports games that target everyone and action games that target players within 13 and 17
years old and above. Our game company can use this heatmap to determine the game's optimal target age to ensure that the game will be
favored once it is released in other regions. Also in figure L, we constructed another heatmap by taking age data for each game to
determine each platform's target age and which platform is the most popular among all video games. Horizontal analysis of the heat map
further reveals that the PS2 is the most popular among all age groups, followed by the X360. As game distributors, we can use this heat
map to select games on the more popular platforms..
# 5. Modelling Methodologies and Assumptions
Answers to the questions above are vital in enabling OldKids to make a sound decision. The questions above will be unraveled with data
visualization tools, trend analysis, and machine learning algorithms.
5.1 Methodologies
For our business case, we aim to produce a regression model that is good enough to reflect the possible correlation between the
independent variables like NA_Sales and our target variable, Other_Sales. This model should have a high enough R2 value and a low
Mean Squared Error (MSE) value to justify the found correlation between independent variables and the dependent variable. Our
dependent variable is Other_Sales, and our independent variables are year of release, platform, genre, publisher, NA_Sales, Critic_Score,
Critic_Count, User_Count, User_Socre, and age.
5.1.1 Data Preprocessing
When approaching Machine Learning problems, the first step is to analyze and apply appropriate preprocessing to the raw data. This
project uses the Video Game Sales dataset that we found on Kaggle with 16719 rows and 16 columns. The dataset exists in the form of a
CSV file, so we first extract the CSV data using Pandas, a widespread Python data manipulation and analysis library. Given the relative
importance of certain variables in our business case, we decided to drop columns such as "Name", "Developer", "Global_Sales", etc. The
next step is to deal with missing values. To be consistent with our approach for data visualization and due to a lack of justification on
possible filler values, we decided to drop rows with missing values. After these steps, we can obtain a clean dataset with 6947 rows and 11
columns.
Moving on , we have noticed some outliers after plotting the box plot for the target variable (Other_Sales). Hence , we have decided to
remove outliers that are more than 2 standard deviations from the mean sales in order to boost model performance. After examining each
column's data types, we realized that the data type for User_Score is an Object, which is incorrect. Hence, we decided to convert it to float.
Next, we split the dependent variable and the independent variables for further preprocessing. The independent variable is saved in a list.
For the dependent variables, we applied one-hot encoding for those with categorical values for regression, namely “Genre”, “Age”,
“Publisher” and “Platform”. With one-hot encoding, a categorical column is converted into one or several columns with binary values. Out of
all these new columns, only one will have a value of 1, and the rest will all be 0. The exact location of the value 1 is unique for each unique
original categorical value, forming a one-to-one relationship. We convert categorical values to sequences of binary values that could be
used easily by regression algorithms to trace the correlation.
After applying one-hot encoding on the categorical independent variables and appending the dependent variable back to the data frame, we
have completed all preprocessing needed. The final processed dataset has 6686 rows and 43 columns. The final step is to use various
regression modeling algorithms and techniques to explore the correlation between the independent and dependent variables.
5.1.2 Regression model training and selection
For the training and comparison of different regression models, we have used the Pycaret library. This high-level, low-code machine
learning library minimizes the code's lines needed with highly encapsulated APIs. After setting up the environment and set “Other_Sales” as
the target variable, we called the compare_models() method in pycaret’s regression module, which will train 19 different regression models
on the provided dataset and tabulate the performance results in sorted order (default is by R2 value).
5.1.3 Result analysis
R-squared (R2) is chosen to account for the model’s performance as it is a goodness of fit for regression models. On top of that, we are also
using mean square error (MSE) to evaluate our prediction's accuracy. It measures the average of the squares of the errors—that is, the
average squared difference between the estimated values and the actual value. We have chosen the XGboost regressor model as our final
model after preliminary benchmarking due to its highest R2 of 0.729 and lowest MSE of 0.0022.

![image](https://user-images.githubusercontent.com/71431944/157259188-ded936e1-3525-4fe0-8125-21cd2277fb4d.png)
5.1.4 XGboost Regressor - Grid Search
To obtain the best performance, we continued to perform grid-search with 10-fold cross-validation to get the model's best parameters. The
final model we have obtained has an r2 value of 0.752 and an MSE of 0.002, which is a good improvement from the original model.
Based on the feature importance plot, we can see that our top 5 most important features include the 3 versions of PlayStations , NA_Sales,
and the publisher named virgin interactive. These observations can also be found in our data visualizations. For instance, NA_Sales is
highly correlated with other sales, and all these versions of PlayStations have achieved high sales in other regions. Also, the feature
importance plot further proves that user_score and critic_score are not significant variables in predicting other sales.

# 6. Limitations
6.1. Recency
Due to the limited data available, this report is only able to cover till 2016. Thus, the scope of this report is constrained till the year 2016.
When updated data are available, a further study can be done to forecast the present economic trend better.
6.2 Model under-representation
We generalize the variable Other_Sales to video game sales of Asia, Africa, and South America in our prediction. This is done to fulfill the
nature of our target group. As a result, we leave regions like Australia out of our discussion. We acknowledge that some degree of under
generalization will affect the accuracy of our prediction. However, we believe that we have covered a sufficient amount of regions in “other
regions'' and the error will be small.
6.3 Model-specificity
As mentioned in the case study above, we believe that there is a lag in game releases in South America, Africa, and China compared to
North America and Europe. On special occasions where there is no lag time, our model might not be helpful.
6.4 Respond rate (user score)
User scores in this data set are not representative of games’ overall rating. From the raw data, we found a lot of missing data in user_socre.
And also, there may be many missing data, such as people who were particularly satisfied with the game or particularly unhappy with the
game not scoring it. Therefore, we believe that the response rate is not comprehensive, and in this respect, user score does not play a good
role in our model and visualization.
6.5 Unavailability of relevant data
Even Though the user_score, critic_score , user_count and critic_count in this dataset may be based on all the regions, we will assume that
the data under these variables are collected in NA region in order to better resolve our business problem as we are unable to find the
relevant data for these variables online.
