# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing


## Data Visualization 


## Data Analysis Process

### What vaccine did the most California kindergartners have in 2015? The least?
1. Add a filter to Column K (Year) and only select the year 2015
2. Scroll to the bottom of the data set and create a new row for "Sums"
3. Take the sum of n first with the following formula: =SUM(E2:E138)
4. Take the sum of nMMR, nDTP, nPolio, nPBE, and nPME with F, G, H, I and J columns instead of E
5. **ANSWER**: In looking at the sums, nPolio had the highest number of kindergartners vaccinated (518,839) and nPME had the lowest (916)
6. **ANSWER**: Percentage wise, this is 94.76% versus 0.16% of all CA kindergartners in 2015
7. Delete the calculations and take off the filter for the year in order to do the next questions

### From 2000 to 2015, were more California kindergartners vaccinated against MMR in public or private schools?
1. Click in the upper left corner of the sheet, go to the "Data" tab, click "Pivot table," then click "CREATE" to create a pivot table from the *entire* data set
2. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
3. Add "nMMR" to the "Values" section of the pivot table settings
4. Create a new sheet by pressing the "+" button in the bottom left of the Google Sheets program
5. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
6. Write the titles for the old headers in the new sheet (school type, n, nMMR) and add a column for % vaccinated 
7. Divide cell C2 by B2 for the percentage of kindergartners vaccinated against MMR in private schools (=C2/B2, then press enter)
8. Divide C3 by B3 for the percentage of kindergartners vaccinated against MMR in public schools (=C3/B3, then press enter)
9. Percentages come out as decimals, must click “format as %” in the row of tools above the sheet
10. **ANSWER**: 91.15% of private school kindergartners are vaccinated against MMR; 94.71% of public school kindergartners are MMR vaccinated

### Which county has the school with the highest MMR vaccination rate?

### List the 3 counties (of the schools) with the lowest MMR and DPT vaccination rates.

### Which years had the highest average vaccination rates for each vaccine?

### How did the total number of students vaccinated against measles/mumps change over time, from 2000 to 2015?

###
