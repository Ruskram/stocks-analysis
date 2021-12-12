# stocks-analysis

# VBA of Wall Street

## Overview of Project

  This project is to help Steve. Steve just graduated with a finance degree. His first clients are his parents who like green energy and put all their investments into DAQO which is a company that makes the silicon that is used in solar panels. Steve doesn't like that they have everything in one investment and would like for them to diversify their invesments. Steve gathered data on some other green energy companies and would like for us to do some analysis. He would like to know which companies would be good options for his parents to diversify their investments into. We provided him a workbook that will analyse the green energy stocks he was looking into, but he would like to expand his research even further.
  
### Purpose
  
  The purpose of this challenge is to expand on the code that we provided to Steve so that he can potentially analyse hundreds if not thousands of stocks. The code we provided him will work but with a large amount of data it can start to get slow. We need to look into improving performance, and if there are thousands of tickers to make the results easier to analyse at a glance.

## Results

The first step that I did was to create seperate arrays for each ticker. The ticker array has 11 items so I made tickerVolumes, tickerStartingPrices, and tickerEndingPrices have arrays of the same number.

![image](https://user-images.githubusercontent.com/92827264/145725228-1973b378-88b9-43aa-9c5c-e74ab514192a.png)

I then initialized the tickerVolumes for each of the tickers. This has to be done before each analysis beacuse we are summing up by row and not just replacing the value like for the starting and ending prices. The for loop below will set each volume of the tickers to 0 then move on to the next line of code.

![image](https://user-images.githubusercontent.com/92827264/145725613-7b75bd34-10a8-439a-87db-f3577ac44889.png)

The next part was to take the for loop that incremented the ticker out and to increment the ticker as the for loop that is going through the rows reaches the last row of the current ticker. This is shown in the image below.

![image](https://user-images.githubusercontent.com/92827264/145725338-4368864f-3f6a-4c4e-b54f-c0ea8368295e.png)

 Finally I made a for loop that will write all the results that was gathered going through the tickers. Since all the data has an array of 11 items, it can all be gathered in one pass instead of going back and forth for each ticker.

![image](https://user-images.githubusercontent.com/92827264/145725524-e2d1c4dc-649c-400b-8e4d-146eb6806758.png)


When I did the analysis of 2017 and 2018 using the original code I came up with the results below:

![image](https://user-images.githubusercontent.com/92827264/145717945-037ab16d-4ea5-4b0c-8ff5-199951497936.png) 
![image](https://user-images.githubusercontent.com/92827264/145718040-1c014d2c-a3d9-4113-ab66-c6940347c26e.png)

After the refactor:

![VBA_Challenge_2017](https://user-images.githubusercontent.com/92827264/145718012-d0f15e64-811f-4971-99bf-5aad4d78287a.png) 
![VBA_Challenge_2018](https://user-images.githubusercontent.com/92827264/145718049-e28ccde9-d680-4724-9d46-c21e212dea3c.png)

As you can see the original code takes about 7x longer to execute than the new refactored code. With the formatting on the cells it makes it much easier to see which 

## Summary

- What are the advantages or disadvantages of refactoring code?

  Some advantages of refactoring code are adding improvements to data/results and optimizing code. When refactoring the code a few key improvements where made like color coding the results of the return so you can tell if it was gain or loss at a glance, or formatting the cells to show a percentage makes readability/understanding much easier. Adding a timer to the code is also an improvement because it allows one to know how much time it would take to analysis different data of similar or greater size. For code optimization, during the refactor we added arrarys to match the amount of tickers so that all the information could be stored in one loop instead of processing one ticker at a time. This allowed the code to execute 85% faster than the original code.
  
  The disadvantages to refactoring code is that you need to go through someone elses code. If there is only a hundred lines of code it might not be that bad, but the longer the code gets it gets much harder to understand and refactor.

- How do those pros and cons apply to the refactoring the original VBA script?

   As you can see from the images the original code took 0.7 seconds to run 12 tickers and the refactored code took 0.15 
