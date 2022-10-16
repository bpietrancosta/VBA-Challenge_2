# VBA-Challenge_2

## Purpose: To provide an analysis of 12 stock price returns using efficient VBA code

### Results of refactored code compared to the original code.
By refactoring the code we were able to produce the same analysis as with the original code. Below we have the elapsed time when running the refactored and original code for each year:

### Original code (2018):
![Original code_timelapse 2018](https://user-images.githubusercontent.com/114181709/196011703-e1e8cfaf-ff08-489d-8944-c971fd504e24.png)

### Refactored code (2018):
![VBA Challenge_2018_timelapse](https://user-images.githubusercontent.com/114181709/196011710-68aafad6-1b2d-4e71-8e37-54eabf681162.png)

### Original code (2017):
![Original code_timelapse 2017](https://user-images.githubusercontent.com/114181709/196011724-1e5e7b85-eb4d-4522-9ea7-573b7814a626.png)

### Refactored code (2017):
![VBA_Challenge_2017_timelapse](https://user-images.githubusercontent.com/114181709/196011731-74ae7772-c4b0-4e86-8a9d-ca094f46332c.png)


### Analysis of refactoring code. 
We were able to reduce the time it takes to execute the code by a factor of 16 for the 2018 analysis and 14 for the 2017 analysis. If you think of this piece of code as n loops within which you have code that takes k time to execute, then to increase the efficiency of your code you can either decrease n or k. Since the tasks in the body of each loop are simple, i.e. summing volumes, checking if the ticker changes and putting data into an array - there isn't much you can do to decrease k.
What you can do is decrease n. In the original code n = i * j, where i = # of tickers and j = # of rows in the data set. Therefore, if you could find a way to get the same analysis from iterating over each data set row once, your new n, call it n' would be defined as n' = n/i. Since n and i are both positive integers greater than 1 that implies n' < n. Therefore, n'*k < n'*k and your code takes less time to execute. This is what we did and it worked.

### Summary
If you were to define the process of refactoring code as a continuous function where the independent variable is time and the dependent variable is the success of refactoring, then you'd have a logarithmic function. What does that mean? That as you initially review code the more obvious areas of improvement will be visible and you will be able to correct them appropriately. However, as you keep spending your time refactoring your code you will get less and less value out of it. You will find a smaller number of errors and the errors that you do find will have less of an impact on the efficiency of your code, for all else equal. Therefore you must find a optimal balance to spend your time most effectively and generate the best code.
