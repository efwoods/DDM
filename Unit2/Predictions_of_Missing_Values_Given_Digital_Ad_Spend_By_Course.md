Predictions of Missing Values in Given Digital Ad Spend By Course
Implementing Collaborative Filtering & Cosine Similarity
================
Evan Woods
2024-01-21

<!-- ## Import Libraries -->
<!-- ## Functions -->
<!-- ## Import Data -->

    # A tibble: 17 × 7
       `Course/Campaign`       `Ad Spend` `Paid Leads` `Paid App Submissions`
       <chr>                        <dbl>        <dbl> <chr>                 
     1 Branded                    1491524        50652 NA                    
     2 General                     974148        21842 NA                    
     3 CORe                        521368         8695 4720                  
     4 Finance                     376960         7957 1833                  
     5 Entrepreneurship            294894         3706 2909                  
     6 Business Analytics          276115         5232 2712                  
     7 Management Essentials       273244         4321 1596                  
     8 Negotiation                 252245         6967 2118                  
     9 Disruptive Strategy         169516         1433 2004                  
    10 Financial Accounting        172689         2005 1408                  
    11 Sustainable Business        160090         2210 1549                  
    12 Leadership Principles       174408         1503 1914                  
    13 Economics                   112047         1328 454                   
    14 Alternative Investments     110574         1539 541                   
    15 Global Business              61802          378 1017                  
    16 Live Courses*               143452          845 364                   
    17 TOTAL                      5565076       120613 25139                 
    # ℹ 3 more variables: `Paid Enrollment` <chr>, `Paid Revenue` <chr>, RAC <chr>

<!-- ## Identifying the Maximum Cosine Similarities -->
<!-- ## Collaborative Filtering To Predict Paid Revenue -->

## Results

    Predicted Values of the Branded Course/Campaign Using Collaborative Filtering &
    Cosine Similarity:

    Course with the Largest Cosine Similarity: Management Essentials

    Cosine Similarity: 0.999835575

    Branded Predicted Paid App Submissions: 8710

    Branded Predicted Paid Enrollment: 3793

    Branded Predicted Paid Revenue: 5856092

    Branded Predicted RAC: 2144

    Predicted Values of the General Course/Campaign Using Collaborative Filtering &
    Cosine Similarity:

    Course with the Largest Cosine Similarity: Live Courses*

    Cosine Similarity: 0.999863424

    General Predicted Paid App Submissions: 2471

    General Predicted Paid Enrollment: 631

    General Predicted Paid Revenue: 1264266

    General Predicted RAC: 10469

    # A tibble: 17 × 5
       `Course/Campaign`       `Ad Spend` `Paid App Submissions` `Paid Enrollment`
       <chr>                        <dbl>                  <int>             <int>
     1 Branded                    1491524                   8710              3793
     2 General                     974148                   2471               631
     3 CORe                        521368                   4720              2655
     4 Finance                     376960                   1833               697
     5 Entrepreneurship            294894                   2909               943
     6 Business Analytics          276115                   2712               942
     7 Management Essentials       273244                   1596               695
     8 Negotiation                 252245                   2118              1056
     9 Disruptive Strategy         169516                   2004              1094
    10 Financial Accounting        172689                   1408               545
    11 Sustainable Business        160090                   1549               689
    12 Leadership Principles       174408                   1914               752
    13 Economics                   112047                    454                98
    14 Alternative Investments     110574                    541               289
    15 Global Business              61802                   1017               371
    16 Live Courses*               143452                    364                93
    17 TOTAL                      5565076                  25139             10919
    # ℹ 1 more variable: `Paid Revenue` <int>

    # A tibble: 17 × 2
       `Course/Campaign`         RAC
       <chr>                   <int>
     1 Branded                  2144
     2 General                 10469
     3 CORe                      196
     4 Finance                   540
     5 Entrepreneurship          312
     6 Business Analytics        293
     7 Management Essentials     393
     8 Negotiation               238
     9 Disruptive Strategy       154
    10 Financial Accounting      316
    11 Sustainable Business      232
    12 Leadership Principles     231
    13 Economics                1143
    14 Alternative Investments   382
    15 Global Business           166
    16 Live Courses*            1542
    17 TOTAL                     509

## Discussion

    The predicted values for the Branded and General courses are higher than other
    courses/campaigns, but the values do not seem to be obvious outliers except
    for the RAC. The predicted RACs are inordinately high with respect to the other
    values in the same column.
