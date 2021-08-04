# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing
* does not include every school in every county

## Data Visualization 
* chloropleth map

## Data Analysis Process

*First, I downloaded the "StudentData.csv," "InfantData.csv" and "pertusisRates2010_2015.csv" files from [Kaggle](https://www.kaggle.com/broach/california-kindergarten-immunization-rates/version/5?select=StudentData.csv) and uploaded them to Google Sheets. Each question below outlines the steps I took to answer it, with the dataset being used marked in step #1 every time. Before beginning the questions, I made sure to "freeze" the top row of columns ("View" tab, then "Freeze," then "1 row"). The questions below build off of one another, so certain steps taken in one question may provide information necessary/referred to in the next.*

### How many California kindergartners got each vaccine each school year?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set to summarize how many students got each vaccine per year
    1. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
        1.  These should appear as columns automatically
    3. Add "year" to the "Filters" section of the pivot table settings and select all but "(Blanks)"
    4. Highlight B2:D18 (the values) and change their format to "number" to produce more readable answers, as shown in the screenshot below
6. **_screenshot 1 here_**

### What percentage of California kindergartners were fully vaccinated in MMR, DTP, and Polio in 2000 versus 2015? How did this number change over time?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set
    1. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "n," "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
    3. Add "year" to the "Filters" section of the pivot table settings and select just 2000 and 2015
3. Copy just the numbers from the pivot table into a new sheet (copying the headers will replicate the entire pivot table) starting in row 2
    1. Write the titles from the pivot table in row 1 ("Year," "n," "nMMR," "nDTP," "nPolio")
4. Although it may not be the same students that are getting each vaccination, it is likely that they are required to have certain vaccinations to be in school and that there is a crossover. For the purpose of this question, I am assuming that the lowest sum in each row is *approximately* how many kindergartners are fully vaccinated against MMR, DTP, *and* Polio. 
    1. Add a new column/column title to cell F1 for "Percent Full" (percent fully vaccinated)
    2. In cells F3 and F4, divide the lowest number in each row ("Sum of nDTP" for both years, cells D2 and D3) by the "Sum of n" for each year (cells B2 and B3) to find the approximate percentage of California kindergartners with each vaccine by the start of the school year
        1. 2000: 497532/521198 = 0.95459 or 95.46% (format as % using Google Sheets tool bar)
        2. 2015: 516030/547520 = 0.9424 or 94.24% (format as % using Google Sheets tool bar)
5. **_At the start of the 2000-2001 school year, approximately 95.46% of California kindergartners (497,532) had each vaccine; at the start of the 2015-2016 school year, approximately 94.25% of California kindergartners (516,030) had each vaccine_**
6. To calculate how the number of full vaccinations changed over time, the percent change formula is (NEW-OLD)/OLD
    1. Add a new row below the table to include this calculation (write the title "Percent Change" in cell C6)
    2. Percent change = (516030-497532)/497532 = 0.037179 or 3.72% increase (format as percent)
7. **_The approximate number of fully vaccinated California kindergartners increased by 3.72% from the 2000 to 2015 school year_**
8. **_screenshot here_**

### Which California county had the most infant Pertussis cases in 2014? Highest death rate?
1. Use InfantData.csv in Google Sheets
2. Sort "Cases" column from Z-->A
3. **_Los Angeles had 143 Pertussis cases in 2014, only 1 of which died_**
4. Sort "County" column from A-->Z to return to original file set-up
5. Add a title to Column F: "DEATH RATE"
    1. In cell F2, write the formula =$D$2/$B$2 (divides the number of deaths by the number of cases)
    2. Double click square in the bottom of the cell to copy the formula down the length of the column
    3. Ignore or delete the contents of any cells in which the #DIV/0! error appears (these counties had 0 Pertussis cases in 2014)
    4. Format the remaining decimals as percentages
    5. To find the highest death rate, sort column F from Z-->A
6. **_Placer County had the highest infant death rate of 33.33% in 2014 (1 in 3 cases died); only 4 counties had any deaths (1 each)_**

### Which California county had the highest rate of Pertussis cases in 2014? How does this county compare to the county with the most infant Pertussis cases in 2014 (found above)?
1. Use pertusisRates2010_2015.csv in Google Sheets
2. Freeze the first column of the sheet so that the county names stay in place when scrolling to distant columns/cases and rates can be easily compared against the counties
3. Sort the "Rate 2014" column from Z-->A to reveal the highest rates at the top of the spreadsheet
4. **_Sonoma County had the highest rate of Pertussis cases in 2014 (142.18 per 100,000 people); although Los Angeles had the most infant Pertussis cases in 2014, the county only had 20.25 cases per 100,000 people in 2014_**

### Between the 2000 and 2015 school years, were more California kindergartners exempt from vaccinations in public or private schools? What percentage of kindergartners in each school type were exempt based on beliefs vs. medical reasons?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set
    1. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "n," "nPBE," and "nPME" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Create a new sheet
    1. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
    2. Write the titles for the old headers in the new sheet (school type, n, nPBE, nPME)
4. Insert a column to the right of "nPME" titled "Sum Exempt" (column E)
    1. Write the following formula in cell E2 and hit enter: =SUM(C2,D2)
    2. Double click the quare in the bottom right of cell E2 to copy the formula down the column: =SUM(C3,D3) and =SUM(C4,D4), respectively
5. Insert a column to the right of "Sum Exempt" titled "Percent Exempt" (column F)
    1. In cell F2, divide the contents of cell E2 by B2 for the percent of of kindergartners with exemptions in private schools (=E2/B2, then press enter)
    2. In cell F3, divide the contents of cell E3 by B3 for the percent of kindergartners with exemptions in public schools (=E3/B3, then press enter)
    3. Format the decimals as percentages
6. **_3.23% of total private school kindergartners were exempt from vaccinations from the 2000 to 2015 school years; 1.81% of total public school kindergartners were exempt from vaccinations_**
7. Insert a new column to the right of "Percent Exempt" titled "Percent Belief" (column G)
    1. In cell G2, divide the contents of cell C2 by E2 (number of private school kindergartners exempt for beliefs by the total number of private school kindergartners exempt)
    2. In cell G3, divide the contents of cell C3 by E3 (number of public school kindergartners exempt for beliefs by the total number of public school kindergartners exempt)
8. **_93.21% of private school kindergartners in California who were exempt from their vaccinations between the 2000 and 2015 school years had "personal belief exemptions"; 91.38% of exempted public school kindergartners were exempt based on beliefs"_**

### List the 5 counties (of the schools) with the highest exemption rates during the 2013-2014 and 2014-2015 school years. How do these counties compare to those with the most Pertussis cases in 2014?
1. Use StudentData.csv in Google Sheets
2. Insert a new column to the right of column J (becomes the new column K), titled "Exempted Sum"
    1. In the first cell of column K (K2), write the formula =SUM($I$2,$J$2) to take the sum of students exempt from vaccinations for belief *and* medical reasons, then double-click the square in the bottom of the cell to copy the formula down the length of the column 
3. Insert a new column to the right of the "Exempted Sum" column (becomes the new column L) titled "Exemption Rate"
    1. In the first cell of column J (J2), write the formula =$K$2/$E$2, column E being "n" (the total number of students in each school in each year) and column K being the total number of students who were exempt for that school/year (calculated in the previous step)
    2. Double-click the square in the bottom of the cell to copy the formula down the length of the column
    3. The formula will produce decimals; re-format the numbers as percentages for easier analysis
4. Sort column L ("Exemption Rate") from Z to A so that the highest 
5. Add a filter to column M ("year") and select only 2013 and 2014 (so that the spreadsheet only shows data from those two school years)
6. **_Riverside (100% exemption at Applied Scholastics Academy in 2013), Sacramento (92.86% at Grace Family Christian School in 2014), Los Angeles (88.24% at The City School in 2013 and 86.67% at Maple Village Waldorf School in 2013), Alameda (86.96% at Berkeley Rose School in 2014), El Dorado (84.21% at Cedar Springs Waldorf School in 2014_**
    1. **_NOTE: All of the exemptions in question were based on beliefs, and all of the schools had less than 25 students_**
7. copy pertussis cases data set into new sheet in the studentdata file
8. use vlookup in column N for most pertussis cases in 2014 (school years overlap, which is why 2013 and 2014 school years would cover this time period)
9. **_second answer here_**

### How did the total number of California kindergarten students with vaccine exemptions change over time, from 2000 to 2015? Personal belief exemptions?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set
    1. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "year" to the "Filters" section of the pivot table settings and select only 2000 and 2015
    3. Add "n," "Exempted Sum," and "nPBE" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
6. Create a new sheet
    1. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
    2. Write the titles for the old headers in the new sheet ("Year," "n, "Exempted Sum," "nPBE")
    3. Create a new row below the table titled "Percent Change"
    4. Use the following formula to calculate the percent change in the total number of exemptions and number of personal belief exemptions from the 2000 school year to the 2015 school year: =(NEW-OLD)/OLD
        1. In cell C6, type "=(10142-10225)/10225" then press enter
        2. In cell D6, type "=(9226-9654)/9654" then press enter
    5. Change the decimals calculated into percentages
7. **_From the 2000-2001 school year to the 2015-2016 school year, the total number of vaccination exemptions decreased by 0.81%; the total number of personal belief exemptions decreased by 4.43%_**
