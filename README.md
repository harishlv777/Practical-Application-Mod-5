## Will a customer accept a coupon?

### Background
“Will a customer accept the coupon?” The goal of this project is to use visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those who did not. 

### Data Analysis jupyter notebook
The data analysis notebook can be found at this public github repository:
https://github.com/harishlv777/Practical-Application-Mod-5

### Data description
This data is from the UCI Machine Learning Repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios, including the destination, current time, weather, and passenger, and then asks people whether they will accept the coupon if they are the driver. There are three possible answers people can choose from:

“Right away”
“Later, before the coupon expires”
“No, I do not want the coupon”
The first two responses are labeled as “Y = 1,” and the third is labeled as “Y = 0.” There are five different types of coupons: Less expensive restaurants (under $20), coffee houses, carryout and takeaway, bars, and more expensive restaurants ($20–$50).

Detailed dataset is available in UC Irvine Machine Learning repository https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation

### Data preparation tasks
The "Coupon.csv" dataset includes driving scenario data, such as destination, time, weather, and passenger details, used to predict whether a person will accept a coupon. It features 12,684 instances with 25 attributes, including categorical and integer data types. Data preparation tasks may involve handling missing values, encoding categorical variables, normalizing continuous features, and splitting the data for classification modeling

Number of Rows: 12,684
Number of Columns: 26
Key Attributes: destination, passenger, weather, time, coupon, expiration, gender, age, etc.
Target Variable: Y (Coupon Acceptance: 1 = Accepted, 0 = Not Accepted)
Some columns represent user behaviors (e.g., frequency of visiting places) and need to be normalized or encoded.

**Column Removal:**
Removed car column due to excessive missing values (~99%).
The car column provides little information due to high missingness and could be removed. Hence, removed car column due to >99% missing values.

**Missing Values & Handling:**
Car column is mostly missing (12,576 missing out of 12,684 rows, ~99%).
A few columns (Bar, CoffeeHouse, CarryAway, RestaurantLessThan20, Restaurant20To50) have minor missing values (<2%).
Filled missing values in columns with <1% missing using the most common value (mode).

**Categorical Value Consolidation:**
Removed or consolidated redundant categorical values to simplify analysis.

**Duplicate Removal:**
Dropped 74 duplicate rows.

**Feature Enhancement:**
Added intuitive columns for Y (coupon acceptance) and direction to improve interpretability.

**Numerical and categorical values:**
The dataset contains a mix of numerical and categorical features. Removed redundant categorical values that denote the same meaning.

## Summary of findings

- Total 12684 coupons were offered
  7146 coupons were accepted. 5450 didnt accept the coupon.
- Coupon distribution
  Customers were offered highest coupons (3987), followed by Restaurant (<20), Carryout, Bar and Restaurant (20-50)
  Expensive restaurants coupons were the least offered 1486
- Coupon distribution was mainly driven by temperature (6464 coupons at 80 degree Farhenheit)
- There was a higher probability of coupon acceptances (based on time of day). Coupons sent out at 2PM showcased highest acceptance probability, while coupons offered at 7am or 10PM showed the least proabability of acceptance.
- Also, total coupons accepted yielded high results especially when coupon expiration is 1Day.
- Drivers in opposite direction accepted more coupons than drivers driving in the same direction.
- Single and Married partners accepted the #of coupons.
- 40.94% proportion of bar coupons were accepted. 1186 didnt accept the coupon, 822 accepted.
  
- For drivers that were offered **bar coupons**
    - 2008 bar coupons were distributed out of which 822 (40.94%) were accepted
    - Drivers who went to bar three or fewer times were 4.32 times more likely to accept a bar coupon 32.92% Coupon     
    acceptance % (three times or fewer) 7.62% (more than three times)
    - Drivers who went to bar more than once a month and were > 25 yrs old accepted coupons had 35.5% acceptance rate, 
    all others had 64.5% acceptance rate.
    - Drivers who go to bars more than once a month, do not have kid passengers, and are in non-farming jobs, accepted 
    coupons 71% of the times (393 out of 551 coupons accepted)
    - Coupon acceptance rates of drivers for Bars and Cheap restaurants included drivers accepting most coupons from 
    cheap restaurants when compared to bars
    - 2775 cheap restaurant coupons were distributed out of which 1963 (70.74%) were accepted
    - Female drivers (with kid passengers) were offered 161 coupons out of which they accepted, 120 coupons at an 75% 
    acceptance rate. Males drivers, when kids were present, on other hand were offered 106 coupons, they accepted 73 
    (68% acceptance rate)
    - Drivers with passengers age 21, 26, 31 received more coupons than the middle age (36,41,46) drivers. 50plus 
    drivers break this trend and receive more coupons than the middle age drivers
    
 #### Hypothesis

Listed below are key hypothesis.

1. Coupons for cheaper restaurants (e.g., Restaurant <20) have a significantly higher acceptance rate compared to bar coupons, indicating price sensitivity among customers.
2. Coupons distributed at 80°F are more likely to be accepted, suggesting that weather conditions, possibly associated with leisure activities, influence acceptance.
3. Coupons distributed at 2 PM have the highest probability of acceptance, aligning with typical meal or break times, while early morning and late-night distribution times yield lower acceptance rates.
4. Coupons with a 1-day expiration period have a higher likelihood of acceptance than those with shorter expiration windows, suggesting that a reasonable time to redeem adds value for customers.
5. Drivers traveling in the opposite direction of the coupon location are more inclined to accept, potentially driven by flexibility in route or intent to visit the location.
6. Single and married partners show higher acceptance rates, suggesting a potential correlation with relationship status and leisure or dining behavior.
7. Drivers visiting bars three or fewer times are more likely to accept bar coupons, suggesting infrequent visitors are more incentivized by discounts.
8. Drivers over 25, without kid passengers, and in non-farming occupations, have the highest bar coupon acceptance rates, indicating that demographics and context heavily influence bar coupon success.
9. Female drivers with kid passengers have a higher acceptance rate for coupons compared to male drivers in similar scenarios, indicating gendered behavior towards convenience or planning.
10. Younger drivers (21, 26, 31) and older drivers (50+) are offered more coupons than middle-aged drivers (36–46), possibly due to targeting strategies based on perceived activity levels and consumer behavior.
11. Drivers are more likely to accept coupons from cheap restaurants than bars, demonstrating a preference for economical dining options.

 ## Next Steps and Recommendations

The analysis presented here is very brief and explores only a couple of coupon types. The following next steps are recommended for further analysis and confirmation of findings:

- Create boxplots or scatterplots to investigate correlations between age, gender, and coupon acceptance.
- Build classification models such as logistic regression, decision trees, random forests, or gradient boosting
- Analyze data to explore acceptance rates of other entities and derive targeted insights
- Explore relationships / correlation of additional variables such as destination, weather, time of day, expiration, income, has children and acceptance rates of coupons
- Develop / explore predictability models for future acceptance of coupons, given this data set and independent variables
- Monitor performance metrics and refine models or strategies iteratively

## Detailed findings and visual explanations

https://github.com/harishlv777/Practical-Application-Mod-5/blob/main/plots/Required%20Assignment%205_Plot%20Summary_hlaxmina.pdf
