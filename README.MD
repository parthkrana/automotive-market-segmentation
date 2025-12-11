# Automotive Market Segmentation Project in R 

## Summary

This project prepared me how to use a number of foundational R concepts, as outlined below:

#### Data Cleaning
<p>
The dataset that I manipulatedcontained information on cars sold in America. After further analyzing the many variables that were present, I decided to contain the data significantly by only assessing the value of used cars sold in the state of Wisconsin. All variables that were insignificant to finding car values were removed to determine the price at which the car was citympg, hwympg, weight, horsepower, rpm, fuel capacity, year, make, model, color, condition, engine type, fuel type, mileage, title status, transmission type, drivetrain, passenger capacity, airbag capacity as well as the type of car sold. In the works of finding more continuous variables and replacing them with discrete variables. Can also turn discrete variables into continuous by implementing a function like One-hot encoding. By creating a binary column for each category level and returning a sparse matrix.

</p>

<p>
  Using R Studio, I was able to find the influential points, or the outliers that greatly affected the slope, of the dataset. We removed 2,523 rows that contained non finite values by creating scatterplots. 87 outliers were also removed due to missing values that were significant to the models that we were creating. 
 </p>
 <p>
I created three histograms using the dataset to better understand the degree of variation and to show the distribution pattern. The histograms created were for price, odometer, and year. The histograms of price and odometer are skewed to the left, while the histogram of year is skewed to the right. Our histogram for price told us that the min value of cars sold in Wisconsin was 0, the max was $109,995, and the average of all cars sold was $13,543. The histogram for odometer told us the minimum value for odometer was 0 miles, the maximum was 150,000, and the mean was 112469 miles. The histogram for year told us that the oldest car sold in Wisconsin in this dataset was a 1954 model year and the newest car was a 2021 model year. The year histogram also told us that most of the cars sold in Wisconsin were from the 2010 model year.
 </p>
 <p>
Using R Studio, I was able to create a model that made it easier for us to calculate predictions for the value of a used car. Our first model made it possible to calculate the price of a car using variables such as odometer and year. I made a total of 3 predictions using our first model. In the first prediction, I used a 2014 car with the price of $15,000 and odometer reading of 20000. The second prediction was a car from 2016 with a $12,100 price and an odometer reading of 59000 miles. Our third prediction was a car from 2005, with a price of $9,000 and 130,000 miles on the odometer. The predictions that model 1 gave us using these variables were: $17216.014 for the first car, $18,382.075 for the second car, and $6,947.624 for the third car. For model 2, I used the same three predictions as model 1. However, model 2 only used the odometer variable to predict the value of a used car. The output for model 2 predictions were: $16,633.49 for the first car, $14,907.05 for the second car and $11,764.03 for the third car. 
 
  </p>

### Exploratory Analysis

<p>
For our Exploratory analysis stage, I started off by creating a few histograms for some of our variables in the dataset(not all), I then followed that by narrowing it down to the variables that I planned on using in our model, which I agreed upon price, odometer, and year. The reasoning behind selecting these variables is as follows, price gives us what a value as to what the car was sold for, this will be our response variables. While the odometer and year variable give us something to use as explanatory variables. I started our explanatory analysis by creating histograms for all the selected variables.

### <b>Details of the Three Histograms: </b> 

#### Histogram #1 

![h1](https://i.ibb.co/gWxwQDX/Screenshot-2022-02-15-at-10-40-32-PM.png)

<br>

#### Histogram #2

![h2](https://i.ibb.co/Ht9f4QH/Screenshot-2022-02-15-at-10-41-39-PM.png)

#### Histogram #3

![h3](https://i.ibb.co/Bybq8Zq/Screenshot-2022-02-15-at-10-42-32-PM.png)

</p>

<p>
  Upon looking at the histograms, I noticed that the histogram for price seems to be skewed to the right. The histogram for odometer is also skewing to the right but it is not as much as price, contrary to price and odometer the histogram for year is skewing to left instead. So, these histograms told us that our data does not require a bit of modifying to be able to use them for our model. To get a better understanding of the skewness, I started off by creating summaries for each of the selected variables. Which showed us the value of price dramatically increased after the 3rd Quadrant, from 18000 to 64000. This explains the skewness in the graph, since there aren’t many values after the 3rd quadrant, but it is causing the skewness. I did the same for odometer and year, which showed us that odometer has the same issue after the 3rd quadrant where the values dramatically increase from 150000 to 290000. This directs us to think that odometer and price have a positive correlation number. I followed our analysis by creating a summary for the year, in which I found the values dramatically increase from Min to 1st quadrant. This directs us to realize that price and year have a negative correlation value.
 </p>
 
 <p>
  After histogram and summaries, I decided to take care of the outliers and influential points. I used the cooks' distance to take care of the outliers. To clearly see the outliers marked by R, I created a graph and added a cutoff line, which then marked all the indexes of the outliers and removed the outliers. I first started with price and odometer, the cooksd graph looked like there are a lot of influential points, especially after the 1300 index. This can also be seen in the outlier’s part, where about 1221 outliers were removed by R. The graph for outliers turned a lot different, especially the midline for the outliers switched from facing in the upward direction to a downward direction.
  </p>
  
  ### Price and Odometer 
  
  #### Cook's Distance Plot

![h4](https://i.ibb.co/ZLSf2Fc/Screenshot-2022-02-15-at-10-13-10-PM.png)

#### ggplot
![h5](https://i.ibb.co/4J28dJm/Screenshot-2022-02-15-at-10-34-21-PM.png)

<p>
  I did the same cooksd influential points and outliers for price and year. The cooksd graph looks like the influential points drastically increase after the 1300 index, this leads us to believe our dataset has some issues after index 1300. Also, there are a lot more outliers with higher than 0.010 cooksd in price and year. I then started working on outliers, and upon running the code the results were quite different from price and odometer, since the code only removed around 3 variables. This makes us believe the cooksd and influential points were a lot like price and odometer, since the number for removed variables was significantly less than before. After taking care of the outliers and influential points I started working on the data mining technique and analysis of results
  </p>
  
### Price and Year

  
  #### Cook's Distance Plot
  ![h6](https://i.ibb.co/zQMh57R/Screenshot-2022-02-15-at-10-37-29-PM.png)
  
  #### ggplot
![h7](https://i.ibb.co/zFntqtK/Screenshot-2022-02-15-at-10-38-22-PM.png)

## Conclusion
In conclusion, building these models helped us predict the price of used cars sold in Wisconsin. Using variables such as year and odometer we were able to predict the price that these cars would sell for. 
