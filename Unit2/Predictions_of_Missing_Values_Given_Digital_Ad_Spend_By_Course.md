Predictions of Missing Values in Given Digital Ad Spend By Course
Implementing Collaborative Filtering & Cosine Similarity
================
Evan Woods
2024-01-23

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

## Predicting ROI

    [1] 17 25

         [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12] [,13] [,14]
    [1,]  774  173  360  337  268  410  473  204  267   325    36   104   163    19
    [2,]  614  111  203  205  148  180  198   95  103   160    26    54    96    34
         [,15]   [,16] [,17]   [,18]   [,19]   [,20] [,21] [,22] [,23]
    [1,]  3913 1491524  3139 1741500 5022400 6763900     3     0     0
    [2,]  2227  974148  1613 1381500 2580800 3962300     3     0     0

          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12] [,13]
     [1,]  714   38   64   75   53   59   65   34   53    50     8    12    40
     [2,]  101  297   23   32   12   21   20   77   11     8     4    24    14
     [3,]   16    9   16   11   10  271   18    6    9    12     2     4     7
     [4,]   22    7    9   11    7   15  193    3    8    10     1     4     6
     [5,]   54   14    8    6    2    4    7   90    4     2     3     4     2
     [6,]   14    4    5    8    9    7    8    2  173     3     0     2     2
     [7,]  116   10   11   16   18   20   25    2   12    90     3     4     5
     [8,]   42    4   10   11    4    8    4    6    5     3     9     3     5
     [9,]   10    2    5    0    3    5    3    1    1     3     1    60     0
    [10,]    9    0    4    2    1    2    7    0    5     1     0     0    10
    [11,]   12    6   12    7    4    8   14    2    6    12     0     1     4
    [12,] 2657  697  944  942  695 1057 1094  545  689   753    98   289   374
          [,14] [,15]   [,16] [,17]   [,18]    [,19]    [,20] [,21] [,22] [,23]
     [1,]     3  1268  521368   554 1606500   886400  2492900     3     0     0
     [2,]     1   645  376960   544  227250   870400  1097650     1     0     0
     [3,]     1   392  252245   376   36000   601600   637600     1     0     0
     [4,]     4   300  169516   278   49500   444800   494300     1     0     0
     [5,]     0   200  172689   146  121500   233600   355100     1     0     0
     [6,]     1   238  160090   224   31500   358400   389900     1     0     0
     [7,]     0   332  174408   216  261000   345600   606600     2     0     0
     [8,]     0   114  112047    72   94500   115200   209700     0     0     0
     [9,]     0    94  110574    84   22500   134400   156900     0     0     0
    [10,]     1    42   61802    33   20250    52800    73050     0     0     0
    [11,]    17   105  143452    93   27000   148800   175800     0     0     0
    [12,]    85 10919 5565076  8262 5978250 13219200 19197450     2     1     1

     [1] 9 1 5 8 3 3 6 0 2 8 0 2

         [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12] [,13] [,14]
    [1,]   39    7  189    6    6   17   14    9   10    13     0     3     6     2
    [2,]   80    9   11  196   11    9   18    6   10     7     5     7    11     2
    [3,]   40    6   14   19  139   21   27    8   12    54     0     3     3     0
         [,15]  [,16] [,17]  [,18]  [,19]  [,20] [,21] [,22] [,23]
    [1,]   321 294894   282  87750 451200 538950     0     0     0
    [2,]   382 276115   302 180000 483200 663200     1     0     0
    [3,]   346 273244   306  90000 489600 579600     1     0     0

    [1] 2 4 2

         [,1] [,2] [,3] [,4] [,5]
    [1,]    0    0    1    0    0
    [2,]    0    0    0    0    1
    [3,]    0    0    1    0    0

    1/1 - 0s - loss: 23.9816 - accuracy: 0.0833 - 186ms/epoch - 186ms/step

           loss    accuracy 
    23.98163795  0.08333334 

    1/1 - 0s - 44ms/epoch - 44ms/step

    [1] 0 0 0
