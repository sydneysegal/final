# Final Project: California Kindergarten Immunization Records

## Story Summary and Sourcing


## Data Visualization 


## Data Analysis Process

### What vaccine did the most California kindergartners have in 2015? The least?
1. added a filter to column k (year) and only selected the year 2015
2. Scrolled to the bottom of the data set and created a new row for sums
3. Took the sum of n first =SUM(E2:E138) then did the same for nMMR, nDTP, nPolio, nPBE, and nPME (with F, G, H, I, and J columns instead of E)
4. In looking at the sums, nPolio had the highest number of kindergartners vaccinated (518,839) and nPME had the lowest (916). Percentage wise, this is 94.76% versus 0.16% of all CA kindergartners in 2015.
5. I then deleted my calculations and took off the filter for the year in order to do the next questions

### From 2000 to 2015, were more California kindergartners vaccinated against MMR in public or private schools?
1. Clicked in upper left, data tab and clicked pivot table, then CREATE to create in a new sheet from the entire data set
2. Rows: schoolType, ascending order
3. Values: nMMR
4. Copy and paste all of the white cells into new sheet (after hitting + in bottom left), leaving room for new headers
5. Write the old headers in (school type, n, nMMR) and add a column for % vaccinated 
6. Divide cell C2 by B2 for the percentage of kindergartners vaccinated against MMR in private schools (=C2/B2, then press enter)
7. Divide C3 by B3 for the percentage of kindergartners vaccinated against MMR in public schools (=C3/B3, then press enter)
8. Percentages come out as decimals, must click “format as %” in row of tools above the sheet
9. 91.15% of private school kindergartners are vaccinated against MMR; 94.71% of public school kindergartners are MMR vaccinated

### Which county has the school with the highest MMR vaccination rate?

### List the 3 counties (of the schools) with the lowest MMR and DPT vaccination rates.

### Which years had the highest average vaccination rates for each vaccine?

### How did the total number of students vaccinated against measles/mumps change over time, from 2000 to 2015?

###
