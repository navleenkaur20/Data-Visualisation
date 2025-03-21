## HW 5 - CS 625, Fall 2023

Navleen Kaur

Due: November 8, 2023

## Part 1: Create Distribution Charts

For this Assignment I choise the second dataset Table 13 - State Population--Rank, Percent Change, And Population Density.

**Q1: boxplot: Show the distributions of the population density (Population per square mile of land area) in 1990, 2000, and 2008
this should result in 3 separate boxplot glyphs in a single chart.**

For this question I selected the three columns from the table under the category Population per square mile of land area for the years 1990, 2000, and 2008. I then used pd.melt to melt the data of years in categories according to the states to make the boxplot.

## Chart 1:
<img src=Images/HW-5-SS-1.png height=500>

* Link to the runnable notebook, <https://colab.research.google.com/drive/1fP-CqyPnvp6F2kUULAOs49LZZF8vtBlm#scrollTo=fxN6hR-8wo4Y>

For manipulating the data in order to create the boxplot I used the pd. melt function in pandas is used to reshape the DataFrame df1 from a wide to a long format. The 'States' column is specified as an identifier and remains unchanged during the transformation process, as indicated by the id_vars=['States'] argument. The var_name='years' argument creates a new column named 'years', which contains the headers from df1 that represent the years. Similarly, value_name='count' generates another new column called 'count', holding the values corresponding to these years. This restructuring is necessary for making the boxplot in question, which visualizes the population per square mile of land area across different years. Originally, df1 had separate columns for each year's population densities for various states. Such a wide format isn't suitable for boxplots that need one column for the categorical variable (years) and another for the quantitative data (population densities), hence the need for melting the DataFrame into a long format. The Data type conversion on the 'count' column of the DataFrame melted_dfn was done using the pd.to_numeric() function from pandas.

The data displays the population per square mile of land area across three different years: 1990, 2000, and 2008. The x-axis is labelled "Years" with three categories the years 1990, 2000 and 2008. The y-axis is labelled "population" and is the count of people per square mile. The population extend from 0 to over 900, based on the highest plotted outlier. Each box represents the interquartile range (IQR) which contains the middle 50% of the data for that year. The bottom of the box shows the first quartile (Q1), the top of the box shows the third quartile (Q3), and the band inside the box shows the median (Q2) of the population distribution. The lines extending from the top and bottom of each box (the "whiskers") represent the range of the data, excluding outliers.

The points above and below the whiskers are plotted individually, these points fall outside the expected range based on the IQR. There is an upward trend in population density over time, as the median (the line inside each box) appears to increase from 1990 to 2008. The range of population densities indicated by the whiskers and the interquartile range of the height of the boxes have increased over time, interpreting greater variance in population density across the measured areas. The spread of data in 2008 is particularly wide, with a large number of outliers, indicating that more areas have significantly higher population densities compared to the other years.

## Advantages:
* The boxplot clearly shows an increasing trend in population density over time. The medians are increasing from 1990 to 2008, suggesting that the central tendency of population density is rising.
* The spread of data can be seen, the spread of the population densities, represented by the size of the boxes, appears to be increasing over time. This suggests that the variability in population density among these states is growing.
* Outliers are clearly marked for each year. It can be seen that there are more outliers in the year 2008 than in 1990, indicating that more states have population densities that fall far from the median.

## Disadvantages:
* The boxplot doesn't show the actual population densities; it only provides a summary. For example, we cannot tell from the plot alone which specific states are outliers or what the exact population densities are.
* It is not clear from the boxplot how many states the data points represent, nor can we tell if the number of states included in each year is the same.

## Observations

Looking at the boxplot it is deduced that states like Connecticut and Delaware, with very high population densities, might be consistent outliers, especially given their high values in the dataset. We can also suggest that states like Alaska with very low population densities are likely contributing to the lower ends of the boxes or whiskers in the plot. The increasing distance between the top of the box and the highest outlier in the year 2008 compared to 1990 indicates an increase in states with very high population densities. 

## Code
```
sns.boxplot(data=melted_df, x="years", y="count")
plt.title("Population per square mile of land area")
plt.xlabel("Years")
plt.ylabel("Population")
```

## Explanation of Code:

- sns is the common abbreviation for the seaborn library.
- boxplot is the function used to generate box plots.
- data=melted_df specifies the DataFrame melted_df as the source of the data.
- x="years" sets the x-axis of the plot to the variable "years" from the DataFrame, indicating that different boxes will be plotted for 
  different years.
- y="count" sets the y-axis to the variable "count" from the DataFrame, which presumably contains the population density values you want 
  to plot.
- plt.title("Population per square mile of land area"): Adds a title to the plot, which is "Population per square mile of land area".
- plt.xlabel("Years"): Labels the x-axis as "Years".
- plt.ylabel("Population"): Labels the y-axis as "Population".




**Q2: eCDF and histogram: Show the distribution of population density in one of the years (your chart title must indicate which year)
your histogram should use a reasonable bin size for the data**

For this chart I selected the year 1960 from the population per square mile of land area column.

## Chart 2
<img src=Images/HW-5-SS-2.png height=500>

* Link to the notebook, <https://colab.research.google.com/drive/1fP-CqyPnvp6F2kUULAOs49LZZF8vtBlm#scrollTo=f0vBKFhL1AuB>

First I created a histogram. To calculate the number of bins I first counted the data points and then took the square root of the data points which was approximately seven and plotted the histogram using seven bins. The histogram shows the frequency distribution of population density (population per square mile of land area) for the year 1960. The x-axis labelled "population", shows intervals of population density while the y-axis labelled count indicates how many areas fall into each population density range. 

The majority of areas have a population density in the range that starts at 0. The tallest bar, which reaches above 35 on the count axis, suggesting that over 35 areas fall into this lowest density range. As the population density increases the frequency (for the count) of the area with that density decreases significantly. The bar height drops sharply after the first interval, indicating fewer areas with higher population densities. There are very few areas with population densities in the higher intervals such as those over 200, 400, 600 and the highest shown category which extends over 800. This is reflected in the very low bars corresponding to these intervals. The histogram shows that in 1960 areas with low population density were much more common than the areas with high population densities and were relatively rare, as shown by the lower frequency of the corresponding bars on the histogram.

## Advantages
- Histogram provides distribution clarity, they give a clear visual of how data is distributed across different ranges. In this case, you can easily see that most states have a lower population density, with a few states having a much higher density.
- Histograms can show the mode(s) of the data. From your histogram, it's evident that the most common range of population density is between 0 and 100, indicating that most states had a low population density in 1960.

## Disadvantages
- Individual data points are grouped into bins, which means loss of granularity of the data. For example, it cannot be deciphered which specific states fall into each bin or their exact population densities.
-  Histograms do not specifically highlight outliers. As it can be seen from the chart there is no way to figure out where outliers are.

## Observations
The largest bar is in the first bin (0-100), suggesting that the majority of states had a population density of less than 100 people per square mile in 1960. The histogram shows a right-skewed distribution, meaning there are a few states with a very high population density, while the rest are relatively low. The bins beyond 200 have significantly fewer states, indicating that high population densities were much less common.

## Code
```
sns.histplot(data=df2, x="1960",bins=7) #binwidth=50
plt.title("Population per square mile of land area for the year 1960")
plt.xlabel("Population")
```

## Explanation of Code
- sns.histplot(data=df2, x="1960", bins=7):
- sns.histplot: This function creates a histogram. A histogram is a graphical representation that organizes a group of data points into user-specified ranges (bins).
- data=df2: This parameter specifies the DataFrame that contains the data.
- x="1960": This specifies that the column named "1960" in the DataFrame df2 should be used for the x-axis values. Each value in this column represents the population per square mile for a state in the year 1960.
- bins=7: This tells the histplot to divide the data into 7 bins (or groups). The range of data will be divided into 7 equal parts, and the number of occurrences within each range will be tallied to create the histogram bars.
- plt.title("Population per square mile of land area for the year 1960"):
plt.title: This function sets the title of the histogram. In this case, the title is "Population per square mile of land area for the year 1960".
- plt.xlabel("Population"):
plt.xlabel: This function sets the label for the x-axis, which in this case is "Population".

## Chart 3

<img src= Images/HW-5-SS-3.png height=500>

* Link to the notebook, <https://colab.research.google.com/drive/1fP-CqyPnvp6F2kUULAOs49LZZF8vtBlm>

This graph depicts the proportion or percentage of data points that are less than or equal to a certain value. On the x-axis, there are values from 0 to 800, which represent the population density (number of people per square mile) in various regions or among different entities being studied in the year 1960. The y-axis ranging from 0.0 to 1.0, shows the cumulative proportion of the dataset falls at or below each x-value. There is a sharp rise in the curve at the beginning suggesting that a significant proportion of the data points have low population density values. The steps in the curve indicate the incremental increases in the proportion of the dataset as the population density value increases. The curve flattens out towards the end, around the 800 mark on the x-axis, indicating that nearly 100% of the data points have a population density of 800 people per square mile or fewer. there are no steps in the curve past the 800 mark, which would suggest there are no recorded population density values higher than this in the dataset. The ecdf provides a visual representation of the distribution of population densities across different areas in 1960, showing how many areas fall into various population density ranges.

## Advantages
- The ECDF shows that the majority of the data points (states) have a low population density relative to the maximum value shown. There is a steep curve near the origin, which indicates that many states have a population density much lower than the maximum.
- The ECDF makes it clear what proportion of states have a population density below any given value. For example, we can see that almost 100% of the states have a population density of less than 800 people per square mile.
## Disadvantages
- The plot flattens out at the higher population densities, which can make it more difficult to discern exact values where there are fewer states. This plateauing can mask the variability among the highest density states.
- While it is clear that most states have a population density less than 200, it's not immediately obvious how many states are at each specific density level within that range.

## Observations
The sharp rise in the ECDF at the lower end suggests a significant concentration of states with low population densities. The curve becomes much less steep after a population density of about 200, indicating that very few states have a population density above this level. The flatness of the curve at the top end suggests there are outliers or states with exceptionally high population density that do not follow the general trend of the dataset.

## Code
```
sns.ecdfplot(data=df2, x='1960')
plt.title("Population per square mile of land area for the year 1960")
plt.xlabel("Years")
plt.ylabel("Population")
```

## Explanation of Code

- sns.ecdfplot(data=df2, x='1960'): This is the main function that creates the ECDF plot. sns is the common abbreviation for the seaborn library.
- data=df2: This specifies that the data used for plotting the ECDF is coming from a pandas DataFrame called df2.
- x='1960': This indicates that the column in the DataFrame df2 that contains the values to be plotted on the x-axis is named '1960'. In this context, it would be the population density values for the year 1960.
- plt.title("Population per square mile of land area for the year 1960"): This line of code sets the title of the plot to "Population per square mile of land area for the year 1960". 
- #plt.xlabel("Years"): This line is commented out.
- plt.ylabel("Population"): This sets the label for the y-axis to "Population". In an ECDF plot, the y-axis typically represents the proportion (or percentage) of data points that are less than or equal to the corresponding x-value.

## Part 2: Further Analysis
For the analysis I chose the first 10 states and arranged them in ascending order according to the values (population per mile square). Following are the findings. 

**Q1:How has population density changed over the years for each state listed in the dataset?
Which state has seen the most significant increase in population density from 1990 to 2008?** 

<img src=Images/HW-5-analysis.png height=500>

* Link to the notebook, https://colab.research.google.com/drive/1K8iNTbiZgv0MiwggpheRsJS3t3V4nCyw

Changes in Population Density from 1990 to 2008 for Each State:

Alaska: Increased from 1 to 1.2 (a change of 0.2)
Colorado: Increased from 31.8 to 47.6 (a change of 15.8)
Arizona: Increased from 32.3 to 57.2 (a change of 24.9)
Arkansas: Increased from 45.1 to 54.8 (a change of 9.7)
Alabama: Increased from 79.6 to 91.9 (a change of 12.3)
Georgia: Increased from 111.9 to 167.3 (a change of 55.4)
California: Increased from 191.1 to 235.7 (a change of 44.6)
Florida: Increased from 239.9 to 339.9 (a change of 100.0)
Delaware: Increased from 341 to 446.9 (a change of 105.9)
Connecticut: Increased from 678.5 to 722.7 (a change of 44.2)
State with the Most Significant Increase in Population Density:

To find the state with the most significant increase, we look for the largest numerical change in population density:

Delaware experienced an increase of 105.9 people per square mile, the largest change of any state listed, followed closely by Florida with an increase of 100.0 people per square mile.
Therefore, Delaware is the state that has seen the most significant increase in population density from 1990 to 2008 according to this dataset.

## Code
```
sns.set_theme(style="whitegrid")
g = sns.catplot(
    data=melted_df, kind="bar",
    x="States", y="count", hue="years",
    errorbar="sd", palette="dark", alpha=.6, height=6
)
g.set_xticklabels(size=10)
g.despine(left=True)
g.set_axis_labels("", "Population per mile square")
g.fig.set_size_inches(12, 6)
g.legend.set_title("")
```

## Explanation of Code
- sns.set_theme(style="whitegrid"): This line of code makes the background of the charts white and adds lines.
- The sns.catplot(...) function is used to create a categorical plot, which in this case is a bar plot:
- data=melted_df: This specifies the DataFrame melted_df as the source of data for the plot.
- kind="bar": This indicates that the plot should be a bar plot.
- x="States": This sets the x-axis to represent the different "States" in the melted_df DataFrame.
- y="count": This sets the y-axis to represent the "count" column in the melted_df DataFrame, which presumably holds numerical data.
- hue="years": This parameter means that within each 'States' category, there will be sub-categories (or hues) based on different "years." Each year will have a different color.

**Q2: Which state has the most substantial rank increase from 1960 to 2008 and what was the percentage change in their rank during this period**

For this analysis I took the rank and percentage change columns from the dataset.
Nevada had the most substantial rank increase moving from 49th in 1960 to 35th in 2008, with more than 30% year over year increase. However,in the period from 1960 to 2008, Nevada experienced a notable change in its state rank. It moved from 49th place in 1960 to 35th place in 2008, marking a significant improvement in its ranking. However, it's important to note that this improvement represents a decrease in rank percentage. Nevada's rank decreased by approximately 28.6% (or increased by approximately 71.4%) during this period, highlighting the dynamic shifts that can occur in state rankings over time.

Here we are trying to find out which state has more than 20% change for that year.

<img src= Images/Hw-5-analysis-ss2.png height=500>

* Link to the notebook, <https://colab.research.google.com/drive/1_ladn6dmWhdel38fEK41P2YH_pZLS9t-#scrollTo=N2cpv0FvwXqn>

Same was done for all the years.

## Code
```
# Filter the dataset for states with major rank increases from 1960 to 1970
major_rank_increases_60s = df[df['PC1960to1970'] > 20]


# Sort the DataFrame based on 'PC1970to1980' column values in descending order
major_rank_increases_60s_sorted = major_rank_increases_60s.sort_values(by='PC1960to1970', ascending=False)

# Create a bar plot for major rank increases in the 1960s
plt.figure(figsize=(12, 6))
sns.barplot(x=major_rank_increases_60s_sorted['States'], y=major_rank_increases_60s_sorted['PC1960to1970'],palette='light:y_r')
plt.title("Major Rank Increases (1960-1970)")
plt.xticks(rotation=360)
plt.xlabel("States")
plt.ylabel("Percentage Change in Rank (1960 to 1970)")

# Show the plot
plt.tight_layout()
plt.show()
```
## Code Expalantion 
- Filter Data: The code selects rows from a DataFrame df where the rank increase percentage (PC1960to1970) from 1960 to 1970 is greater than 20%.
- major_rank_increases_60s includes values whose percentage increase is greater than 20.
- major_rank_increases_60s_sorted: Sorted view of the dataframe in descending order based on the PC1960to1970 values.
- Create Plot: A bar plot is created using seaborn, with state names on the x-axis and their respective rank increase percentages on the y-axis. The bars are colored using a gradient from light yellow to red.
- Customize Plot: The plot's size is set, and the x-axis labels are attempted to be rotated by 360 degrees 
- Display Plot: The layout is adjusted for a neater appearance, and the plot is displayed with title and axis labels.

Then I created a line chart to confirm that our analysis holds true everywhere.

<img src=Images/Hw-5-analysis-ss-3.png height=500>

* Link to the chart, <https://colab.research.google.com/drive/1_ladn6dmWhdel38fEK41P2YH_pZLS9t-#scrollTo=afqphg9lzdP9>

I created a new data frame which calculates Year-Over-Year percentage changes in rank for each state, and then creates a line plot to visualize these changes over time. The legend shows the different percent change YOY for comparison.

## Code
```
newdf = pd.read_excel(file_path)
# Remove spaces from column names
newdf.set_index('States', inplace=True) 
newdf.columns = newdf.columns.str.replace(' ', '')
newdf.rename(columns = {'%change1960to1970':'PC1960to1970','1970to1980PC':'PC1970to1980','PC1980to1990.1':'PC1980to1991'}, inplace = True)

# Calculate the year-over-year percentage change in rank for each state
rank_columns = ['Rank1960', 'Rank1970', 'Rank1980', 'Rank1990', 'Rank2000', 'Rank2008']
for i in range(1, len(rank_columns)):
    year1 = rank_columns[i - 1]
    year2 = rank_columns[i]
    newdf[f'PC{year1}to{year2}'] = ((newdf[year2] - newdf[year1]) / newdf[year1]) * 100

# Plot the year-over-year rank changes for all states
plt.figure(figsize=(12, 6))
sns.lineplot(data=newdf[['PC1980to1991', 'PC1990to2000', 'PC2000to2008']], legend='brief')
plt.title("Year-over-Year Percentage Change in Rank Among States")
plt.xlabel("Year")
plt.ylabel("Percentage Change in Rank")


plt.xticks(rotation=90)

# Show the plot
plt.tight_layout()
plt.show()
```
## Code Explanation

- `newdf.set_index('States', inplace=True)` set index as States so it can be used on x-axis. So states can be treated as indexes.
- `newdf.columns = newdf.columns.str.replace(' ', '')` there were spaces in some column names so I removed the spaces.
-  Renamed few of the columns just to be consistent.
-  Created new columns in the dataframe to calculate the year over year percentage change in the rank for each state by using 
  `newdf[f'PC{year1}to{year2}'] = ((newdf[year2] - newdf[year1]) / newdf[year1]) * 100`
-  Then I created a line chart for year over year percenatge change in rank among states using seaborn.
  


## References
1. qimacros, <https://www.qimacros.com/histogram-excel/how-to-determine-histogram-bin-interval/>
2. Pandas Documentation, <https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html>
3. Stackoverflow, <https://stackoverflow.com/questions/6390393/how-to-change-tick-la>
4. geeksforgeeks, <https://www.geeksforgeeks.org/matplotlib-figure-figure-set_size_inches-in-python/>
5. aspiring youths, <https://aspiringyouths.com/advantages-disadvantages/histogram/>
6. sciencing, <https://sciencing.com/advantages-disadvantages-box-plot-12025269.html>
