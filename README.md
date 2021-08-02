# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing
* does not include every school in every county

## Data Visualization 


## Data Analysis Process

### What vaccine did the most California kindergartners have in 2015? The least?
1. Add a filter to Column K (Year) and only select the year 2015
2. Scroll to the bottom of the data set and create a new row for "Sums"
3. Take the sum of n first with the following formula: =SUM(E2:E138)
4. Take the sum of nMMR, nDTP, nPolio, nPBE, and nPME with F, G, H, I and J columns instead of E
5. **_ANSWER: In looking at the sums, the highest number of kindergartners were vaccinated against Polio (518,839) and the fewest kindergartners had personal medical exemptions from being vaccinated (PME; 916). Percentage wise, this is 94.76% versus 0.16% of all CA kindergartners in 2015._**
6. Delete the calculations and take off the filter for the year in order to do the next questions

### From 2000 to 2015, were more California kindergartners vaccinated against MMR in public or private schools?
1. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
2. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
3. Add "nMMR" to the "Values" section of the pivot table settings
4. Create a new sheet by pressing the "+" button in the bottom left of the Google Sheets program
5. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
6. Write the titles for the old headers in the new sheet (school type, n, nMMR) and add a column for "percent vaccinated" (column D)
7. Divide cell C2 by B2 for the percent of of kindergartners vaccinated against MMR in private schools (=C2/B2, then press enter)
8. Divide C3 by B3 for the percent of kindergartners vaccinated against MMR in public schools (=C3/B3, then press enter)
9. The percentages come out as decimals first, must click the column letter (D) to highlight the whole column, “format as %” in the row of tools above the sheet
10. **_ANSWER: 91.15% of private school kindergartners are vaccinated against MMR; 94.71% of public school kindergartners are MMR vaccinated_**

### List the 5 counties (of the schools) with the highest exemption rates from 2000 to 2015.
1. right click column K and insert 1 column left (becomes the new column K), titled "exemption sum"
2. formula: =SUM($I$2,$J$2), then double click the square in the bottom of the cell so that it copies the formula down the length of the column
3. right click column K ("exemption sum") and insert a column right (column L), titled "exemption rate" 
4. formula: =$K$2/$E$2, column E being "n"
5. Double click the square in the bottom of the cell so that it copies the formula down the length of the column
6. rates come out as decimals, must click the column letter (L) to highlight the whole column, then “format as %” in the row of tools above the sheet
7. click the down arrow next to the column letter (still L), select "sort sheet Z-->A"
8. **_ANSWER: Napa (100% at Kolbe Academy in 2012), Riverside (100% at Applied Scholastics Online Academy in 2013), Alameda (100% at Muhammad University O in 2003 and 2004), Marin (100% at North Bay Christian Academy in 2001), Santa Cruz (97.22% at Santa Cruz Waldorf in 2010)
9. Important to note that the schools are different sizes... some religious...

### List the 3 counties (of the schools) with the lowest MMR vaccination rates from 2000 to 2015.
1. 

### Which years had the lowest average vaccination rates for each vaccine? Highest exemption rates?
1. 

### How did the total number of students vaccinated against measles/mumps change over time, from 2000 to 2015?
1. 

### How did the total number of students with vaccine exemptions change over time, from 2000 to 2015? Personal medical exemptions vs. belief exemptions?
1.

### Which California elementary school had the highest number of medical or belief exemptions, from 2000 to 2015?
1. 
