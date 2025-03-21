# HW 3 - CS 625, Fall 2023

Navleen Kaur  
Due: October 25, 2023
# Dataset 1

For this assignment I have chosen the third dataset 
* Table 102 - Expectation of Life at Birth, and Projections
* Table 107 - Death Rates by Age, Sex, and Race
  
**Q1: Using Table 102, compare life expectancy for people born between 1970-1999 for the four categories, "Male", "Female", "White", "Black".**

<img src=Images/Hw-4-chart-1-excel.png height=500>

* Link to the chart: <https://github.com/odu-cs625-datavis/fall23-mcw-navleenkaur20/blob/main/HW-4/Book1.xlsx>

In the visualization created using Excel, columns like "TOTAL MALE," "TOTAL FEMALE," "TOTAL WHITE," and "TOTAL BLACK" from Table 102 have been depicted using a multi-line chart. Given that the data spans over various years, a line chart is apt for illustrating such time-series data. Such charts emphasize continuity and can effectively highlight fluctuations over time. With this representation, it's straightforward to pinpoint patterns and trends in the dataset. For instance, the chart showcases a noticeable upward trajectory in the life expectancy of females at birth. The ability to plot multiple series like "Total Male," "Total Female," "Total Black," and "Total White" on one graph ensures we can draw comparisons across these categories effortlessly. The graph reveals that while the life expectancy for females is the most promising, that of the total black population lags behind, even as overall life expectancy trends upward.

Idiom: Multiple Line Chart / Mark: Points with line connection
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Years | key, ordinal | horizontal position on a common scale (x-axis) |
| Life Expectancy | value, Quantitative| vertical spatial region (y-axis) |
| Gender/Race | Key, categorical | color hue |





**Q2: Using Table 107, compare infant mortality rates (under 1 year) for these same categories between 1980-1999.**

<img src= Images/HW-4-chart-2-excel.png height=500>

* Link to the chart, <https://github.com/odu-cs625-datavis/fall23-mcw-navleenkaur20/blob/main/HW-4/book2.xlsx>


From the dataset, I opted for the columns "Black Male," "BLACK FEMALE," "WHITE MALE," and "WHITE FEMALE,," omitting the "TOTAL MALE" and "TOTAL FEMALE" columns due to inconsistencies with the year data. Instead of substituting with zeros, which could be misinterpreted as a complete absence of infant deaths for those years, I decided it was more accurate and clearer to remove them entirely. This ensures the data remains undistorted, steering clear of potential misreadings stemming from zero values. A multi-line chart is once again the most suitable visualization for this dataset. I used Excel to create this chart.
For this set of data, I employed a multi-line chart to analyze and contrast the infant mortality rate over the years, clearly indicating a trend of decreasing rates as time progresses.
Utilizing a multi-line chart facilitates an effective comparison of the trends in "Black Male," "Black Female," "White Male," and "White Female" categories simultaneously. This gives a clear understanding of the performance of each demographic over the years, making it evident that there's a steady reduction in infant mortality rates across all categories.

Idiom: Multiple Line Chart / Mark: Points with line connection
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Years | key, ordinal | horizontal position on a common scale (x-axis) |
| Infant Mortality Rate (Rates per 1,00,000)| value, Quantitative| vertical spatial region (y-axis) |
| Gender/Race | Key, categorical | color hue |


## Further Questions
Q1: How has the total population (both male and female) changed over the years?

Hypothesis: The total population has been increasing over the years.

Q2: Is there a consistent gender gap in the total population every year?

Hypothesis: There is a consistent trend where females outnumber males in the total population every year.

Q3. How does the growth trend of the White population compare to that of the Black population over the years?

Hypothesis: The White population has been growing at a similar rate to the Black population over the years.

The answers for the above questions can be searched through Table 9. Resident Population, by Race and Age	
Table 6. Resident Population by Sex, Race, and Hispanic Origin Status	

## Extra Credit:

**Combine the data from Tables 102 and 107 to investigate how infant mortality might affect overall life expectancy.**


  <img src=Images/hw-4_chart-3-dataset-3.png height=400>
  
* Link to the chart: <https://github.com/odu-cs625-datavis/fall23-mcw-navleenkaur20/blob/main/HW-4/book2.xlsx>

- I took the average of male and female infant mortality rates from table 107 to get the overall infant mortality rate. Then, I combined this data with the total life expectancy rate from Table 102 for the common years from 1960 to 2006.

- There appears to be a negative correlation between infant mortality rate and life expectancy. As the infant mortality rate increases, life expectancy tends to decrease. This is suggested by the roughly linear descending pattern of the data points. Most of the data points (1980-2006) are clustered around a life expectancy close to 80 years, indicating that many of the regions or samples have a similar life expectancy, regardless of the variations in infant mortality rates.

Idiom: Scatter Plot / Mark: Points
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Life Expectancy (years) | value, Quantitative| vertical spatial region (y-axis) |
| Infant Mortality Rate (Rates per 1,00,000)| value, Quantitative| horizontal spatial region (x-axis) |


## Recreating the Charts:

<img src= Images/HW-4-RECEATE-CHART-1-PY.png height=400>

* Link to the chart: <https://colab.research.google.com/drive/1c0yez5Zo6u80iHJhi-5BKE9qnscrQDQA#scrollTo=rxaTKHpmfCa6>

I utilized Python libraries—seaborn, matplotlib, and pandas—to replicate the charts. 
- I first adjusted the x-axis range, setting it between 1970 and 2000 to align with the Excel chart. The x-axis is labeled as "Years". 
- The y-axis displayed the life expectancy rates based on the dataset's range, and was appropriately labeled "Life Expectancy". 
- I color-coded the lines consistent with the original Excel chart, with "TOTAL MALE" in blue, "TOTAL FEMALE" in orange, "BLACK TOTAL" in green, and "WHITE TOTAL" in red. 
- Each line was also marked with dotted markers. 
- I opted to exclude the grid for a cleaner look. 
- The legend was placed outside the chart, specifically in the upper right corner, enclosed within a grey box, mirroring the initial Excel chart's presentation.

<img src= Images/HW-4-chart-2-excel.png height=400>

* Link to the chart: <https://colab.research.google.com/drive/1c0yez5Zo6u80iHJhi-5BKE9qnscrQDQA#scrollTo=rxaTKHpmfCa6>

- I again used Python with libraries like seaborn, matplotlib, and pandas to make charts similar to the Excel one. 
- I set the years from 1990 to 1999 to match the earlier Excel chart about infant deaths. The x-axis is named "Years" and the y-axis shows the "Infant Mortality Rate" from our data.
- I colored the lines just like in the Excel chart: "WHITE MALE" is blue, "BLACK MALE" is orange, "WHITE FEMALE" is green, and "BLACK FEMALE" is red.
- I added dots to the lines and removed the grid. The chart's legend is in the top right corner with a grey box around it, like the Excel chart.




## Dataset 2 (Complete the full assignment with one of the other datasets).
For the extra credits I chose the second dataset Table 118 - Death Rates for Major Causes of Death--States and Island Areas.

**Q1: Which states had the highest death rates over all causes in 2006?**

<img src=Images/HW-4-DS-2-CH-1.png height=600>

* Link to the chart: <https://colab.research.google.com/drive/1c0yez5Zo6u80iHJhi-5BKE9qnscrQDQA#scrollTo=rxaTKHpmfCa6>

I removed data from North Dakota, Vermont, Wyoming, Virgin Islands, Guam, American Samoa, and Northern Marianas, as well as any HIV-related data because these entries had missing or unreliable values marked as (s). This was done to ensure the accuracy of the results.
I decided to use a bar chart to answer the initial question because it's a suitable way to compare different categories, in this case, the states. This type of chart makes it easy to see and compare the total death rates for all states. States are a type of categorical data, and bar charts are a good choice for representing and comparing categorical data, like different states in this dataset.
Bar charts are simple and easy to understand. In this case, each bar in the chart shows the total death rate for a specific state, making it straightforward to grasp the differences between states at a glance. Bar charts are arranged according to the length, whether it's from the highest to the lowest death rates. This flexibility helps reveal patterns and trends. When identifying the state with the highest total death rate, a bar chart is especially useful because it quickly shows you the state with the tallest bar, which corresponds to the highest total death rate. To make the bar chart, I used the y-axis to represent the states, and on the x-axis, I calculated the sum of all values in each row, and I stored this total in the 'Total Death Rate' column.


Idiom: Bar Chart / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| States |key, categorical| vertical spatial region (y-axis) |
|Death Rate| value, Quantitative| horizontal spatial region (x-axis) |

**Q2:  Is this ordering different if you compare deaths due to disease vs. deaths due to accident, injury, and assault? In other words, which states are more hazardous to your health vs. which states are the most dangerous?**

<img src=Images/HW-4-ss-9.png height=500>

* Link to the chart: <https://colab.research.google.com/drive/1c0yez5Zo6u80iHJhi-5BKE9qnscrQDQA#scrollTo=rxaTKHpmfCa6>
  
For this question, I added all values from these columns together 'Disease of Heart', 'Maglinent neoplasm cancer',' Cerebovascular diseases', 'Chronic lower respiratory diseases',' Diabetes Mellitus',	'Alzheimer's disease',' influenza and pneumonia,	'Nephritis, nephrotic syndrome and nephrosis' and named it "Total death due to diseases". Then I added columns 'Total accidents', 'injury by firearms' , and 'assault', and named the column 'Death due to accidents'. Then I sorted the states according to the values.

I used this multiple bar chart because horizontal layout ensures that each state's name is easily readable. This makes it straightforward to identify and compare death rates for specific states across both causes of death. The bar charts placed side by side make it easy to visually compare the magnitude of deaths due to diseases versus accidents for each state. Both datasets are presented side by side, allowing for a direct comparison between disease-related deaths and accident-related deaths for each state without the need to slide downside to compare the chart. The use of different colors (blue for diseases and red for accidents) helps in clearly distinguishing between the two causes of death. The length of each bar provides an immediate visual representation of the number of deaths, making it simple to discern which states have higher or lower rates. The horizontal bar graph format, with its clear labeling, consistent scale, and distinct color coding, provides an effective means to compare and analyze the dataset for deaths due to diseases and accidents by state. Therefore, I used this multiple bar chart. 

The first part of the chart ranks U.S. states based on the total number of deaths attributed to diseases. States are ordered from highest to lowest in terms of deaths due to diseases. The horizontal bars represent each state and the length of each bar corresponds to the total number of deaths in that state. The charts give an insight that Mississippi has the highest number of deaths due to diseases, while Hawaii has the lowest. The second section is based on the total number of deaths due to accidents. States are again ordered from highest to lowest in terms of deaths due to accidents. The horizontal bars for each state depict the total number of deaths caused by accidents, injuries and assaults. Again in the second chart, Mississipi tops the chart, indicating the highest number of deaths due to accidents, while New York has the lowest.





Idiom: Bar Chart / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| States |key, categorical| vertical spatial region (y-axis) |
|Death due to various diseaes| value, Quantitative| horizontal position on a common scale (x-axis) |

Idiom: Bar Chart / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| States |key, categorical| vertical spatial region (y-axis) |
|Death due to accidents, injury, assault| value, Quantitative| horizontal position on a common scale (x-axis) |


## Further Questions
Q1: Which age group is more prone to certain type of diseases?

Hypothesis: Older generation must be more prone to diseases of heart and diabeties.

Q2: Do states with higher heart disease mortality rates also exhibit higher overall mortality rates?

Hypothesis: States with higher mortality rates due to heart diseases will also have higher overall mortality rates, suggesting a correlation between heart disease prevalence and general health outcomes in the state.

Answers for the above questions can be searched through the this dataset and Table 117.

## References
  1. Geeksforgeeks,<https://www.geeksforgeeks.org/python-seaborn-tutorial/>
  2. Seaborn User guide and tutorial ,<https://seaborn.pydata.org/tutorial.html>
  3. Seaborn An introduction to Seaborn, <https://seaborn.pydata.org/tutorial/introduction.html>
  4. Datacamp, <https://www.datacamp.com/tutorial/python-seaborn-line-plot-tutorial>
  5. Geeksforgeek, <https://www.geeksforgeeks.org/python-pandas-melt/>
  7. Stackoverflow, <https://stackoverflow.com/questions/22483588/how-to-plot-multiple-dataframes-in-subplots>
  8. Statology, <https://www.statology.org/pandas-subplots/>
