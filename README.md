---
title: "[]{#_lywijnrmk675 .anchor}Will the Customer Accept the Coupon?"
---

By: Deep Joshi

Github repo: [[https://github.com/deepjoshi1/berkeley_ai_ml_assignment_mod5_coupon]{.underline}][1]

-   Notebook: **customer_and_coupon.ipynb**

-   Data set: **data/coupons.csv**

[[Introduction]{.underline}][2]

[[Data Description]{.underline}][3]

[[Analysis]{.underline}][4]

> [[Understanding Data]{.underline}][5]
>
> [[Coupon Types]{.underline}][6]
>
> [[Coupon type: Bar]{.underline}][7]
>
> [[Conclusion]{.underline}][8]
>
> [[Coupon type: Restaurant(\<20)]{.underline}][9]
>
> [[Coupon type: Coffee House]{.underline}][10]
>
> [[Conclusion]{.underline}][11]
>
> [[Coupon type: Carry out & Take away]{.underline}][12]
>
> [[Conclusion]{.underline}][13]

# Introduction

This analysis explores whether customers will accept coupons in various driving scenarios. The study uses data from a survey conducted on Amazon Mechanical Turk, where participants were presented with different driving situations and asked if they would accept a coupon. The survey considered factors such as destination, time of day, weather, and passenger.

# Data Description

This data is from the UCI Machine Learning Repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios, including the destination, current time, weather, and passenger, and then asks people whether

they will accept the coupon if they are the driver. There are three possible answers people can choose from:

-   "Right away"

-   "Later, before the coupon expires"

-   "No, I do not want the coupon"

The first two responses are labeled as "Y = 1," and the third is labeled as "Y = 0." There are five different types of coupons: Less expensive restaurants (under \$20), coffee houses, carryout and takeaway, bars, and more expensive restaurants (\$20--\$50).

# Analysis 

[The analysis uses Python with the pandas, Matplotlib, and Seaborn libraries to process and visualize the survey data. After cleaning the data by handling missing values, the analysis focuses on different coupon types and identifies key demographic and situational factors that correlate with higher acceptance rates.]{.mark}

[This information can be valuable for businesses seeking to optimize their coupon distribution strategies by targeting specific customer segments and scenarios for maximum impact.]{.mark}

## Understanding Data

![][14]

Using the info() method of dataframe shows a few columns such as Bar, CoffeeHouse are missing some values but column cars are missing lots of values. To Get another perspective of msising data let's further check the missing values in %.

data.isnull().mean() \* 100

![][15]

[It clearly shows that the car is missing values in 99% cases so it makes sense to drop this column and fill the rest missing categorical values with the mode.]{.mark}

## Coupon Types

There are 5 types of coupons with the following count and accepted count

  ------------------------------------------------------------------------------------------------------------------------
  **[coupon]{.mark}**              **[total_count]{.mark}**   **[accepted_count]{.mark}**   **[acceptance_rate]{.mark}**
  -------------------------------- -------------------------- ----------------------------- ------------------------------
  [Coffee House]{.mark}            [3996]{.mark}              [1995]{.mark}                 [.499249]{.mark}

  [Restaurant(\<20)]{.mark}        [2786]{.mark}              [1970]{.mark}                 [0.707107]{.mark}

  [Carry out & Take away]{.mark}   [2393]{.mark}              [1760]{.mark}                 [0.735478]{.mark}

  [Bar]{.mark}                     [2017]{.mark}              [658]{.mark}                  [0.410015]{.mark}

  [Restaurant(20-50)]{.mark}       [1492]{.mark}              [1970]{.mark}                 [0.441019]{.mark}
  ------------------------------------------------------------------------------------------------------------------------

## ![][16]

## 

## Coupon type: Bar

Dataframe is filtered for coupon type "Bar" for this analysis and stored in variable bar_coupons.

Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.

-   Acceptance rate of those who went to a bar 3 or fewer times a month: 37.07%

-   Acceptance rate of those who went to a bar more than 3 times a month: 76.88%

Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to all others. Is there a difference?

-   Acceptance rate between drivers who go to a bar more than once a month and are over the age of 25: 69.52%

-   Acceptance rate rest: 39.33%

-   Driver with age over 25 and and who go to bar more than once a month has acceptance rate difference: 30.19%

```{=html}
<!-- -->
```
-   Acceptance rate for drivers, go to bars more than once a month, had passengers that were not a kid, and were not widowed: 71.32

Acceptance rate for drivers, go to bars more than once a month and are under the age of 30: 72.17%

-   Acceptance rate for drivers, go to cheap restaurants more than 4 times a month and income is less than 50K: 45.35

-   Acceptance rate for drivers, go to bars more than once a month, had passengers that were not a kid, and were not widowed: 71.32

-   Acceptance rate for drivers, go to bars more than once a month and are under the age of 30: 72.17%

-   Acceptance rate for drivers, go to cheap restaurants more than 4 times a month and income is less than 50K: 45.35

### Conclusion

-   **Data-driven observation:** The provided data shows a high acceptance rate (76.88%) for coupons among drivers who visit bars more than three times a month. This suggests a correlation between bar visits and coupon acceptance.

-   **Targeted demographic:** Furthermore, the data indicates that drivers under 30 who frequent bars exhibit a strong coupon acceptance rate (72.17%). This highlights a specific demographic (young, bar-going drivers) with a higher propensity for using coupons.

[This hypothesis suggests that targeting ride-sharing coupons towards drivers who frequent bars, particularly those under 30 and those who are not transporting children, could result in higher acceptance and usage rates.]{.mark}

## Coupon type: Restaurant(\<20)

Drivers with age under 30 has acceptance rate of: 73.61 %

Drivers with age above 30 has acceptance rate of: 68.32 %

Conclusion

[To achieve the highest acceptance rate for \"Restaurant(\<20)\" coupons, it\'s optimal to offer them to drivers under age 30.]{.mark}

## Coupon type: Coffee House

![][17]

### Conclusion

[To maximize the acceptance rate for \"Coffee House\" coupons, it\'s recommended to target drivers with a friend as a passenger, particularly around 7AM or 10AM or 2PM with friends. This specific scenario leads to a higher acceptance rate compared to other passenger combinations or times of the day.]{.mark}

## Coupon type: Carry out & Take away

![][18]

### Conclusion

[To achieve the highest acceptance rate for \"Carry out & Take away\" coupons, it\'s optimal to offer them during lunch and dinner hours (2PM and 6PM).]{.mark}

  [1]: https://github.com/deepjoshi1/berkeley_ai_ml_assignment_mod5_coupon
  [2]: #introduction
  [3]: #data-description
  [4]: #analysis
  [5]: #understanding-data
  [6]: #coupon-types
  [7]: #coupon-type-bar
  [8]: #conclusion
  [9]: #coupon-type-restaurant20
  [10]: #coupon-type-coffee-house
  [11]: #conclusion-1
  [12]: #coupon-type-carry-out-take-away
  [13]: #conclusion-2
  [14]: media/image2.png {width="3.9198097112860895in" height="3.6614588801399823in"}
  [15]: media/image1.png {width="3.9166666666666665in" height="3.2395833333333335in"}
  [16]: media/image3.png {width="5.90625in" height="5.989583333333333in"}
  [17]: media/image5.png {width="5.947916666666667in" height="4.5in"}
  [18]: media/image4.png {width="5.90625in" height="4.770833333333333in"}
