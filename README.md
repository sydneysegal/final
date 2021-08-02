# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing
* does not include every school in every county

## Data Visualization 


## Data Analysis Process

#### First, I downloaded the "StudentData.csv" and "InfantData.csv" files from [Kaggle](https://www.kaggle.com/broach/california-kindergarten-immunization-rates/version/5?select=StudentData.csv) and uploaded them to Google Sheets. Each question below outlines the steps I took to answer it, with the data set being used marked in step #1 every time. Before beginning the questions, I made sure to "freeze" the top row of columns ("View" tab, then "Freeze," then "1 row").

### How many California kindergartners had each vaccine in 2014 and 2015?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
4. Add "nMMR," "nPolio," and "nDTP" to the "Values" section of the pivot table settings, making sure that they are summarizing by "SUM"
5. Add "year" to the "Filters" section of the pivot table settings and select just 2014 and 2015
6. Highlight B2:C3, change format to "number" then move the decimal point to the left twice
7. (insert photo here)
8. ANSWER:

### How many California kindergartners were fully vaccinated in MMR, Polio, and DTP in 2000 versus 2015?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. 

### How did the total number of fully vaccinated Kindergarten students change over time, from 2000 to 2015?
1. Use StudentData.csv in Google Sheets

### Which California county had the most Pertussis cases in 2014?
1. Use InfantData.csv in Google Sheets
2. Sort "Cases" column from Z-->A (hover over the B column until you see a down arrow)
3. **_ANSWER: Los Angeles had 143 Pertussis cases in 2014, only 1 of which died_**

### Which California county had the highest infant death rate from Pertussis cases in 2014?
1. Use InfantData.csv in Google Sheets
2. Add a title to Column F: "DEATH RATE"
3. Formula: =$D$2/$B$2 (divide deaths by cases)
4. Double click square in the bottom of the cell to copy the formula down the length of the column
5. Format as %
6. Sort Z-->A
7. **_ANSWER: Only 4 counties had any deaths in 2014 (1 death); Placer County had the highest infant death rate of 33.33% (1 in 3 cases died)_**

### From 2000 to 2015, were more California kindergartners vaccinated against MMR in public or private schools?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
4. Add "nMMR" to the "Values" section of the pivot table settings
5. Create a new sheet by pressing the "+" button in the bottom left of the Google Sheets program
6. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
7. Write the titles for the old headers in the new sheet (school type, n, nMMR) and add a column for "percent vaccinated" (column D)
8. Divide cell C2 by B2 for the percent of of kindergartners vaccinated against MMR in private schools (=C2/B2, then press enter)
9. Divide C3 by B3 for the percent of kindergartners vaccinated against MMR in public schools (=C3/B3, then press enter)
10. The percentages come out as decimals first, must click the column letter (D) to highlight the whole column, “format as %” in the row of tools above the sheet
11. **_ANSWER: 91.15% of private school kindergartners are vaccinated against MMR; 94.71% of public school kindergartners are MMR vaccinated_**

### List the 5 counties (of the schools) with the highest exemption rates from 2000 to 2015.
1. Use StudentData.csv in Google Sheets
2. right click column K and insert 1 column left (becomes the new column K), titled "exemption sum"
3. formula: =SUM($I$2,$J$2), then double click the square in the bottom of the cell so that it copies the formula down the length of the column
4. right click column K ("exemption sum") and insert a column right (column L), titled "exemption rate" 
5. formula: =$K$2/$E$2, column E being "n"
6. Double click the square in the bottom of the cell so that it copies the formula down the length of the column
7. rates come out as decimals, must click the column letter (L) to highlight the whole column, then “format as %” in the row of tools above the sheet
8. click the down arrow next to the column letter (still L), select "sort sheet Z-->A"
9. **_ANSWER: Napa (100% at Kolbe Academy in 2012), Riverside (100% at Applied Scholastics Online Academy in 2013), Alameda (100% at Muhammad University O in 2003 and 2004), Marin (100% at North Bay Christian Academy in 2001), Santa Cruz (97.22% at Santa Cruz Waldorf in 2010)_**
10. Important to note that the schools are different sizes... some religious...

### List the 3 counties (of the schools) with the lowest MMR vaccination rates from 2000 to 2015.
1. Use StudentData.csv in Google Sheets

### Which years had the lowest average vaccination rates for each vaccine? Highest exemption rates?
1. Use StudentData.csv in Google Sheets

### How did the total number of students with vaccine exemptions change over time, from 2000 to 2015? Personal medical exemptions vs. belief exemptions?
1. Use StudentData.csv in Google Sheets

### Which California elementary school had the highest number of medical or belief exemptions, from 2000 to 2015?
1. Use StudentData.csv in Google Sheets
