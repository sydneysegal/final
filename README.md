# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing
* does not include every school in every county

## Data Visualization 
* chloropleth map

## Data Analysis Process

*First, I downloaded the "StudentData.csv," "InfantData.csv" and "pertusisRates2010_2015.csv" files from [Kaggle](https://www.kaggle.com/broach/california-kindergarten-immunization-rates/version/5?select=StudentData.csv) and uploaded them to Google Sheets. Each question below outlines the steps I took to answer it, with the data set being used marked in step #1 every time. Before beginning the questions, I made sure to "freeze" the top row of columns ("View" tab, then "Freeze," then "1 row").*

### How many California kindergartners got each vaccine each school year?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
4. Add "nMMR," "nPolio," and "nDTP" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
6. Highlight B2:C3, change format to "number" 
7. **_(TotalVaccinated photo here)_**

### What percentage of California kindergartners were fully vaccinated in MMR, Polio, and DTP in 2000 versus 2015? How did this number change over time?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
4. Add "n," "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
5. Add "year" to the "Filters" section of the pivot table settings and select just 2000 and 2015
6. copy numbers into new sheet
7. freeze, bold headings
8. change number format
9. look for the lowest sum in each row (that is how many are vaccinated in everything?)
10. ANSWER PART 1
11. ...
12. ANWER PART 2

### Which California county had the most infant Pertussis cases in 2014? Highest death rate?
1. Use InfantData.csv in Google Sheets
2. Sort "Cases" column from Z-->A (hover over the B column until you see a down arrow)
3. **_Los Angeles had 143 Pertussis cases in 2014, only 1 of which died_**
4. Sort "County" column from A-->Z to return to original file set-up
5. Add a title to Column F: "DEATH RATE"
6. Formula: =$D$2/$B$2 (divide deaths by cases)
7. Double click square in the bottom of the cell to copy the formula down the length of the column
8. Format as %
9. Sort Z-->A
10. **_Placer County had the highest infant death rate of 33.33% in 2014 (1 in 3 cases died); only 4 counties had any deaths (1 each)_**

### Which California county had the highest rate of Pertussis cases in 2014? How does this county compare to the one found in part 1 of the question above?
1. Use pertusisRates2010_2015.csv in Google Sheets
2. Sort the "Rate 2014" column from Z-->A by hovering over the column letter (K) and clicking the down arrow that appears
3. **_Sonoma County had the highest rate of Pertussis cases in 2014 (142.18 per 100,000 people); although Los Angeles had the most infant Pertussis cases in 2014, the county only had 20.25 cases per 100,000 people in 2014_**

### How did the total number of students with vaccine exemptions change over time, from 2000 to 2015? Personal belief exemptions?
1. Use StudentData.csv in Google Sheets
2. 

### Between the 2000 and 2015 school years, were more California kindergartners exempt from vaccinations in public or private schools? What percentage of kindergartners in each school type were exempt based on beliefs vs. medical reasons?
1. Use StudentData.csv in Google Sheets
2. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
3. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
4. Add "n," "nPBE," and "nPME" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
5. Create a new sheet by pressing the "+" button in the bottom left of the Google Sheets program
6. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
7. Write the titles for the old headers in the new sheet (school type, n, nPBE, nPME)
8. Insert a column to the right of "nPME" by right-clicking, title it "Sum Exempt" (column E)
9. Write the following formula in cell E2 and hit enter: =SUM(C2,D2)
10. Double click the quare in the bottom right of cell E2 to copy the formula down the column: =SUM(C3,D3) and =SUM(C4,D4), respectively
11. Insert a column to the right of "Sum Exempt" by right-clicking, title it "Percent Exempt" (column F)
12. In cell F2, divide the contents of cell E2 by B2 for the percent of of kindergartners with exemptions in private schools (=E2/B2, then press enter)
13. In cell F3, divide the contents of E3 by B3 for the percent of kindergartners with exemptions in public schools (=E3/B3, then press enter)
14. The percentages come out as decimals first, so click on "F" to select the whole column and select "Format as %" in the tool bar
15. **_3.23% of total private school kindergartners were exempt from vaccinations from the 2000 to 2015 school years; 1.81% of total public school kindergartners were exempt from vaccinations_**
16. Insert a new column to the right of "Percent Exempt" titled "Percent Belief" (column G)
17. In cell G2, divide the contents of cell C2 by E2 (number of private school kindergartners exempt for beliefs by the total number of private school kindergartners exempt)
18. In cell G3, divide the contents of cell C3 by E3 (number of public school kindergartners exempt for beliefs by the total number of public school kindergartners exempt)
19. **_93.21% of private school kindergartners in California who were exempt from their vaccinations between the 2000 and 2015 school years had "personal belief exemptions"; 91.38% of exempted public school kindergartners were exempt based on beliefs"_**
20. (screenshot of all parts here)

### List the 5 counties (of the schools) with the highest personal belief exemption rates during the 2015 school year.
1. Use StudentData.csv in Google Sheets

*need to redo steps starting here*
3. right click column K and insert 1 column left (becomes the new column K), titled "exemption sum"
4. formula: =SUM($I$2,$J$2), then double click the square in the bottom of the cell so that it copies the formula down the length of the column
5. right click column K ("exemption sum") and insert a column right (column L), titled "exemption rate" 
6. formula: =$K$2/$E$2, column E being "n"
7. Double click the square in the bottom of the cell so that it copies the formula down the length of the column
8. rates come out as decimals, must click the column letter (L) to highlight the whole column, then “format as %” in the row of tools above the sheet
9. click the down arrow next to the column letter (still L), select "sort sheet Z-->A"
10. **_Napa (100% at Kolbe Academy in 2012), Riverside (100% at Applied Scholastics Online Academy in 2013), Alameda (100% at Muhammad University O in 2003 and 2004), Marin (100% at North Bay Christian Academy in 2001), Santa Cruz (97.22% at Santa Cruz Waldorf in 2010)_**
11. Important to note that the schools are different sizes... again, some religious...
