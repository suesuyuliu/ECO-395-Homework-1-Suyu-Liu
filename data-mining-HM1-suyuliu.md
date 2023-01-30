## 1) Data visualization: flight at ABIA

-   What is the best time of day to fly to minimize delays, and does
    this change by airline?

The figure 1 takes the scheduled departure time of the flight as the
abscissa and the average departure delay as the ordinate, showing the
average departure delay of the plane every hour of day in 2008. For the
departure time, 5am to 6am is the best period with the least average
flight departure delay time. According to the figure1, flights during
this time even departed earlier.

    ## Error in newABIA %>% drop_na(DepDelay) %>% group_by(CRSDepTimegroup) %>% : could not find function "%>%"

    ## Error in transform(newABIA_summary, name = 1): object 'newABIA_summary' not found

    ## Error in theme_set(theme_bw()): could not find function "theme_set"

    ## Error in position_dodge(0.1): could not find function "position_dodge"

    ## Error in ggplot(newABIA_summary, aes(x = CRSDepTimegroup, y = avg_DepDelay, : could not find function "ggplot"

Figure 1: Line graph of the flight departure delay of the time of day

-   Does this change by airline?

The figure 2 shows the average departure delay time per day by airline.
Upon Figure 2, the situation of each airline is very different. The best
time of day to fly to minimize delays changes by airline. US airline is
the most punctual airline. UA’s flight at 8:00 p.m. is even delayed by
an average of more than 150 minutes.

    ## Error in newABIA %>% drop_na(DepDelay) %>% group_by(CRSDepTimegroup, UniqueCarrier) %>% : could not find function "%>%"

    ## Error in ggplot(newABIA_summary_1): could not find function "ggplot"

Figure 2: Bar graph of the flight departure delay by the time of day and
different airlines

## 2) Wrangling the Olympics

1.  The 95% of heights for female competitors across all athletics
    events is 183.00.

<!-- -->

    ## Error in olympics_top20 %>% filter(sport == "Athletics", sex == "F"): could not find function "%>%"

    ## Error in olympics_top20_height %>% summarise(q95_heights = quantile(height, : could not find function "%>%"

    ## Error in eval(expr, envir, enclos): object 'v' not found

1.  Swimming Women’s 100 metres Butterfly was the single women’s event
    with the greatest variability in competitor’s heights. The following
    table shows the top 7 women’s events, both team and individual, in
    which the heights of female competitors vary the most.

<!-- -->

    ## Error in olympics_top20 %>% filter(sex == "F") %>% group_by(event) %>% : could not find function "%>%"

    ## Error in knitr::kable(olympics_top20_fe, align = "cccc"): object 'olympics_top20_fe' not found

1.  The average age of Olympic swimmers

-   How has the average age of Olympic swimmers changed over time?

Upon figure 1, the average age of swimmers has fluctuated over time
around the age of 20. From 1900 to 1912, the average age increased a
lot. From 1912 to around 1931, the average age dropped again from over
25 to under 20. From then until 1975, the average age remained around
20. Since 1975, the age of the players has increased over time.

    ## Error in olympics_top20 %>% filter(sport == "Swimming"): could not find function "%>%"

    ## Error in olympics_top20_swimming %>% group_by(year) %>% summarise(avg_age = mean(age)): could not find function "%>%"

    ## Error in ggplot(ageovertime): could not find function "ggplot"

Figure 1: Line graph of average age of Olympic swimmers changed over
time

-   Does the trend look different for male swimmers relative to female
    swimmers? The average age of both male and female swimmers has
    increased over time since 1950. However, since 1925, the average age
    of female swimmers has been lower than that of male swimmers.

<!-- -->

    ## Error in olympics_top20_swimming %>% group_by(year, sex) %>% summarise(sex_avg_age = mean(age), : could not find function "%>%"

    ## Error in ggplot(sex_ageovertime): could not find function "ggplot"

Figure 2: Line graph of average age of Olympic swimmers changed over
time by sex

## 3) K-nearest neighbors: cars

-   Method: I use the K-fold cross validation to get optimal K.

1.  Split the data into a training and a testing set with 5 folds
    randomly.
2.  RMSE and prediction.
3.  Find the minimum RMSE under different K values(1-300 & 1-233).
4.  Plot the fitted model with optimal K.

# Trim 350

-   The plot of RMSE versus K. The following is the minimum RMSE,
    corresponding to k is 15.

<!-- -->

    ## Error in sclass %>% filter(trim == "350"): could not find function "%>%"

    ## Error in eval_select_impl(NULL, .vars, expr(c(!!!dots)), include = .include, : object 'sclass_350' not found

    ## Error in analysis(x): object 'sclass_350_split' not found

    ## Error in assessment(x): object 'sclass_350_split' not found

    ## Error in crossv_kfold(sclass_350, k = K_folds): could not find function "crossv_kfold"

    ## Error in map(sclass_350_folds$train, ~knnreg(price ~ mileage, k = 2, data = ., : could not find function "map"

    ## Error in map2_dbl(models, sclass_350_folds$test, modelr::rmse): could not find function "map2_dbl"

    ## Error in foreach(k = k_grid, .combine = "rbind") %dopar% {: could not find function "%>%"

    ## Error in cv_grid %>% arrange(err) %>% head(1): could not find function "%>%"

    ## Error in eval(expr, envir, enclos): object 'mink_350' not found

    ## Error in ggplot(cv_grid): could not find function "ggplot"

-   For the optimal value of K(15), show a plot of the fitted
    model–predictions vs. x.

<!-- -->

    ## Error in knnreg(price ~ mileage, data = sclass_350_train, k = 15): could not find function "knnreg"

    ## Error in sclass_350_test %>% mutate(price_pred = predict(knn15, sclass_350_test)): could not find function "%>%"

    ## Error in ggplot(data = sclass_350_test): could not find function "ggplot"

    ## Error in eval(expr, envir, enclos): object 'p_test' not found

## Trim: 65AMG

-   The plot of RMSE versus K. The following is the minimum RMSE,
    corresponding to k is 12.

<!-- -->

    ## Error in sclass %>% filter(trim == "65 AMG"): could not find function "%>%"

    ## Error in eval_select_impl(NULL, .vars, expr(c(!!!dots)), include = .include, : object 'sclass_65AMG' not found

    ## Error in analysis(x): object 'sclass_65AMG_split' not found

    ## Error in assessment(x): object 'sclass_65AMG_split' not found

    ## Error in crossv_kfold(sclass_65AMG, k = K_folds): could not find function "crossv_kfold"

    ## Error in foreach(k2 = k_grid_2, .combine = "rbind") %dopar% {: could not find function "%>%"

    ## Error in cv_grid_2 %>% arrange(err_2) %>% head(1): could not find function "%>%"

    ## Error in eval(expr, envir, enclos): object 'mink_65AMG' not found

    ## Error in ggplot(cv_grid_2): could not find function "ggplot"

    ## Error in knnreg(price ~ mileage, data = sclass_65AMG_train, k = 12): could not find function "knnreg"

    ## Error in sclass_65AMG_test %>% mutate(price_pred = predict(knn12, sclass_65AMG_test)): could not find function "%>%"

    ## Error in ggplot(data = sclass_65AMG_test): could not find function "ggplot"

    ## Error in eval(expr, envir, enclos): object 'p_test' not found

## Which trim yields a larger optimal value of K? Why do you think this is?

The 350(K=15) yields a large optimal value of K than 65AMG(K=12).
Because the 350’s(416) number of observations is larger than the
65AMG’s(292). For a better balance between bias and variance, the 350
with larger observations needs a larger K.
