# J124 Final Project: *California Kindergarten Immunization Records*

## Story Summary and Sourcing
2014 and 2015 were big years for disease transmission in California, especially among children, between a [measles outbreak](https://www.cdc.gov/mmwr/preview/mmwrhtml/mm6406a5.htm) linked to visits to Disneyland theme parks and a [pertussis “epidemic”](https://www.cdc.gov/mmwr/preview/mmwrhtml/mm6348a2.htm). However, since 2000, the rate of vaccine exemption has increased more than two-fold (211.59%). Not only have many parents been [hesitant](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6515949/) to vaccinate their children in recent years, with beliefs that vaccines could cause autism or overwhelm young immune systems, but permanent medical exemptions (PMEs) actually tripled from [2015 to 2018](https://www.aafp.org/news/health-of-the-public/20181127califvaccstudy.html) after California attempted to increase vaccination rates by banning personal belief exemptions (PBEs). Ultimately, that is to say that many families have objected to vaccinating their children at key moments in public health history –– and especially in counties in the northern half of California (as shown in the data visualization below). Specifically, from 2013 to 2016, 23 California counties had overall exemption rates that were both above the state average (4.94%) and the recommended herd immunity level of [about 95% vaccinated](https://www.who.int/immunization/sage/meetings/2017/october/2._target_immunity_levels_FUNK.pdf). While the number of exemptions did decrease slightly during the same years (21% from 2013 to the end of 2016), **it would be valuable to investigate why there might be a *geographic trend* in vaccine refusal or exemptions**. For example, the higher exemption rates in one area could suggest that there is some sort of urban/rural divide, being higher in smaller and less urban counties. Additionally, some of the top 7 schools with the highest exemption rates are from within these counties, like Sacramento and El Dorado. These schools are not necessarily representative of the whole state, though they show how vaccination may be linked to values; each school is private, with 20 or fewer students, one in the northern part of California is religious and made the list twice, etc. With exemption rates as high as 92.86% in *non-online* schools from 2013 to 2016, it is clear that outbreaks of vaccine-preventable illnesses remain possible and immunization/education remains important.

| Human Source | Contact Information | Why? | 
| ----------- | ----------- | ----------- |
| Dr. Richard Pan | District office: 916-262-2904, Capitol office: 916-651-4006 | Dr. Pan is a pediatrician and current State Senator representing Sacramento County. As a Northern California doctor and policy-maker, Dr. Pan could provide an expert perspective, having written a number of state bills about vaccine exemptions. For example, Pan’s [Senate Bill 277](https://sd06.senate.ca.gov/2015-2016-legislation) abolished personal belief exemptions in 2015 to “ensure that all children can safely attend school.” |
| Laura Shain | lshain@lagunitas.org, 415-488-4118 ext. 202 | Shain is the principal of two public schools in the Lagunitas School District in Marin County. From the 2013 to 2015 school years, Marin’s overall exemption rate was not the highest but also too high to meet the threshold for “herd immunity,” so it could be valuable to know how Shain feels as a school administrator about being responsible for children who aren’t fully immunized. In a previous [ABC News article](https://abcnews.go.com/Health/inside-anti-vaccine-enclaves/story?id=28693645), she expressed feeling scared about the possibility of a measles outbreak since the school encourages vaccination. |
| Joshua Nerius | josh.nerius@servicenow.com | Nerius wasn’t vaccinated as a child and contracted measles in 2016. He is based in Chicago and has been previously interviewed for several national stories, though he or his parents (two anti-vaxxers) would still be valuable to understand the perspective of those who have been affected firsthand by vaccine exemption or to lead me to other sources in the anti-vax community. |

| Published Source | Why? |
|-----|-----|
| [“The Effectiveness of California Assembly Bill 2109”](/Effectiveness-CA-Bill-2109.pdf) by Dr. Lilli Goishi-Bessey | Dr. Goishi-Bessey’s work would be helpful because it looks at the 10 most populous counties in California, the same years that my proposed story and visualization do, as well as exemptions *between* the school years (not just at the start of them) and specific reasons for *personal belief exemptions* (i.e., religion or counseling from a Health Care Practitioner). The report pulls from other open access data from the CA Department of Public Health that I could use, though Goishi-Bessey synthesizes it well, especially in relation to state legislation. For example, she links the decrease in PBEs from the 2013 to 2015 school years to the implementation of AB 2109 in 2012 that requires that parents seeking PBEs receive education about vaccine safety. |
| [“Kindergartners with All Required Immunizations"](/Kidsdata-All-Required.csv) from 2013-2019, organized by KidsData.org | Since the StudentData dataset does not include how many students were fully immunized, the KidsData dataset fills in this gap. For example, some parents might choose not to exempt their children from every immunization (or some lower-income communities might not have had access to all necessary vaccines), but the original dataset doesn't make this distinction. The KidsData.org [webpage](https://www.kidsdata.org/topic/292/immunizations-kindergarteners/map#loct=3&fmt=63&tf=84&center=-13325098.893387,4509031.392449&zoom=1) also presents the data in a choropleth map which shows how Northern California has had lower vaccination rates over time, complementing what I found about the region's high exemption rates. However, there is a discrepancy between the schools/school districts listed in each of these datasets (i.e., the Larkspur-Corte Madera School District does not have its elementary schools listed in the StudentData dataset), so I would make sure to note that in my story. |

## Data Visualization 
[![Percentage of kindergartners exempt from vaccination in each California county, 2013 to 2015 school years,'The data is presented on a choropleth map of California, with a range of light to dark colors for low to high exemption rates in each county'](/DataViz2.png)](https://datawrapper.dwcdn.net/NzQ3v/3/)

## Data Analysis Process

*First, I downloaded the "StudentData.csv," "InfantData.csv" and "pertusisRates2010_2015.csv" files from [Kaggle](https://www.kaggle.com/broach/california-kindergarten-immunization-rates/version/5?select=StudentData.csv) and uploaded them to Google Sheets to perform the following analyses. I did not clean any of these sheets beforehand but paid attention for anomalies as I went. Each question below outlines the steps I took to answer it, with the final version of the dataset being used marked/linked in each step 1. Before beginning the questions, I made sure to "freeze" the top row of columns. The questions also build off of one another, so certain steps taken in one question may provide information referred to in the next.*

### #1: How many California kindergartners got each vaccine each school year?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Create a pivot table from the *entire* data set to summarize how many students got each vaccine per year
    1. Add "year" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
        1.  The "Values" added should automatically appear as columns in the pivot table
    3. Add "year" to the "Filters" section of the pivot table settings and select all but "(Blanks)"
    4. Highlight the values in the pivot table and change their format to "number" to produce more readable answers, as **_shown in the screenshot below_**
        1. ![Breakdown of vaccinations by year,'total number of kindergartner MMR DTP and Polio vaccinations by year'](/YearBreakdown.png)
        2. **_Most notable from the answers above is that the highest number of students were vaccinated against MMR, DTP, and Polio in 2015 (517k, 516k, and 518k, respectively); the second-highest number of students for all three vaccinations occurred in 2000 (497k, 497k, and 500k), the first school year that the data was recorded_**

### #2: What percentage of California kindergartners were fully vaccinated in MMR, DTP, and Polio in the 2000-2001 versus 2015-2016 school year? How did this number change over time?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Create a pivot table from the *entire* data set to summarize how many students received each vaccine in 2000 vs. 2015
    1. Add "year" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "n," "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
    3. Add "year" to the "Filters" section of the pivot table settings and select just 2000 and 2015
3. Copy just the numbers (including years) from the pivot table into a new sheet (copying the column headers will replicate the entire pivot table) to do more non-pivot table analysis
    1. Write the titles from the pivot table in row 1 of the new sheet ("Year," "n," "nMMR," "nDTP," "nPolio")
4. Although it may not be the same students that are getting each vaccination, it is likely that they are required to have certain vaccinations to be in school and that there is a crossover. For the purpose of this question, I am assuming that the lowest sum in each row is *approximately* how many kindergartners are fully vaccinated against MMR, DTP, *and* Polio. 
    1. Add a new column for "Percent Full" (percent of kindergartners who are fully vaccinated)
    2. Divide the lowest "Sum of nDTP" for both years by the "Sum of n" for each year to find the approximate percentage of California kindergartners with each vaccine by the start of the school year
        1. 2000: 497532/521198 = 0.95459 or 95.46% (format as percent)
        2. 2015: 516030/547520 = 0.9424 or 94.24% (format as percent)
5. **_At the start of the 2000-2001 school year, approximately 95.46% of California kindergartners (497,532) had each vaccine; at the start of the 2015-2016 school year, approximately 94.25% of California kindergartners (516,030) had each vaccine_**
6. Add a new row below the table called "Percent Change"
    1. To calculate how the number of full vaccinations changed over time, the percent change formula is =(NEW-OLD)/OLD
    2. Percent change = (516030-497532)/497532 = 0.037179 or 3.72% increase (format as percent)
7. **_The approximate number of fully vaccinated California kindergartners increased by 3.72% from the 2000-2001 to 2015-2016 school year_**
    1. ![Approximate Number of Fully Vaccinated CA Kindergartners from 2000 to 2015,'Google Sheets table of vaccination breakdown for California kindergartners in 2000 and 2015 with percent fully vaccinated based on lowest number for individual vaccines'](/FullVax.png)

### #3: Which California county had the most infant Pertussis cases in 2014? Highest case rate? Highest death rate?
1. Use the [InfantData](/InfantData.csv) dataset
2. Sort "Cases" column from Z-->A to organize the counties with the most infant Pertussis cases at the top
3. **_Los Angeles had 143 Pertussis cases in 2014, only 1 of which died_**
    1. ![Top 5 California Counties With Most Infant Pertussis Cases in 2014,'Los Angeles County had the most pertussis cases in infants in 2014](/InfantCases.png)
5. Sort "Case Rate" column from Z-->A to show the counties with the most Pertussis cases per 1,000 infants at the top
6. **_Madera County had the highest case rate for infants with Pertussis in 2014 (6.1 per 1,000 infants), with just 7 cases total_**
7. ![Top 5 California Counties With Highest Infant Pertussis Case Rates in 2014,'Google Sheets screenshot of InfantData.csv file sorted by highest to lowest case rate'](/InfantRate.png)
8. Sort "County" column from A-->Z to return to original file set-up
9. Add a new column called "DEATH RATE"
    1. In the first cell of the new column, divide the number of deaths by the number of cases
    2. Drag the square in the bottom of the cell to the bottom of the column (row 59) to copy the formula down the length of the column
        1. Make sure that the formula has changed by row for each cell (i.e., D3/B3 for row 3, D4/B4 for row 4, etc.)
    3. Delete the contents of any cells in which the #DIV/0! error appears (these counties had 0 Pertussis cases in 2014)
    4. Format the remaining decimals as percentages
    5. To find the highest death rate, sort the column from Z-->A
10. **_Placer County had the highest infant death rate of 33.33% in 2014 (1 in 3 cases died); only 4 counties had any deaths (1 each for Santa Barbara, Joaquin, and Los Angeles too)_**
    1. ![Infant Death Rate by Pertussis in 2014 in the Top 5 California Counties,'Google Sheets table of the top 5 California counties with the highest death rates of infants with pertussis in 2014'](/InfantDeath.png)

### #4: Which California county had the highest rate of Pertussis cases in 2014? How does this county compare to the county with the most infant Pertussis cases in 2014 (found above)?
1. Use the [pertusisRates2010_2015](/pertusisRates2010_2015) dataset
2. Freeze the first column of the sheet so that the county names stay in place when scrolling to other column (so that cases/rates can be easily compared against the counties)
3. Sort the "Rate 2014" column from Z-->A to reveal the highest rates at the top of the spreadsheet
4. **_Sonoma County had the highest rate of Pertussis cases in 2014 (142.18 per 100,000 people); although Los Angeles had the most infant Pertussis cases in 2014 (2.1 per 1,000 infants according to Kaggle and included in the table above), the county only had 20.25 cases per 100,000 people in 2014_**
    1. **_Comparing just the Los Angeles figures, Los Angeles County had 10 times as many Pertussis cases in infants than they did the whole population in 2014 (2.1 cases per 1,000 infants is equivalent to 210 cases per 100,000 infants)_**
    2. ![California County with Most Pertussis cases versus Los Angeles in 2014,'Sonoma County had the highest rate of Pertussis cases in 2014 at 142.18 per 100k people and Los Angeles had only 20.25 per 100k people'](/PertussisRates.png)

### #5: Between the 2000-2001 and 2015-2016 school years, were more California kindergartners exempt from vaccinations in public or private schools? What percentage of kindergartners in each school type were exempt based on beliefs vs. medical reasons?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Create a pivot table from the *entire* data set to summarize how many students had what type of vaccine exemption in public vs. private schools
    1. Add "schoolType" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "n," "nPBE," and "nPME" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Create a new sheet to do more non-pivot table analysis
    1. Copy and paste all of the white cells (everything but the column headers) from the pivot table into this new sheet, leaving room for new headers
    2. Write the titles for the old headers in the new sheet (school type, n, nPBE, nPME)
4. Insert a column to the right of "nPME" (in the new sheet) called "Sum Exempt"
    1. Use the SUM formula in the first cell of this new column to add together the number of kindergartners with belief and medical exemptions
        1. Ex. =SUM(C2:D2)
    2. Double click the quare in the bottom right of the cell to copy the formula down the column
        1. Ex. =SUM(C3:D3)
5. Insert a column in the new sheet called "Percent Exempt" 
    1. In the first cell of the new column, divide the "Sum Exempt" for private schools by the total number of students in private schools ("n" column) for the percent of of kindergartners with exemptions in private schools (ex. =E2/B2, then press enter)
    2. In the second cell of the column, divide the "Sum Exempt" for public schools by the total number of students in public schools ("n" column) for the percent of of kindergartners with exemptions in public schools
        1. Ex. =E3/B3, then press enter
    3. Format the decimals as percentages
6. **_3.23% of total private school kindergartners were exempt from vaccinations from the 2000-2001 to 2015-2016 school years; 1.81% of total public school kindergartners were exempt from vaccinations_**
7. Insert a new column in the new sheet called "Percent Belief"
    1. Divide the number of private school kindergartners exempt for beliefs by the total number of private school kindergartners exempt
    2. Divide the number of public school kindergartners exempt for beliefs by the total number of public school kindergartners exempt
8. **_93.21% of private school kindergartners in California who were exempt from their vaccinations between the 2000-2001 and 2015-2016 school years had "personal belief exemptions"; 91.38% of exempted public school kindergartners were exempt based on beliefs"_**
    1. ![Vaccination Exemptions by School Type,'summary statistics of vaccination exemptions in public and private schools in California from 2000 to 2016'](/SchoolType.png)

### #6: List the 5 counties (of the schools) with the highest exemption rates during the 2013-2014, 2014-2015, and 2015-2016 school years.
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Insert a new column in the main sheet called "Exempted Sum"
    1. In the first cell of the new column, take the sum of students exempt from vaccinations for belief *and* medical reasons, then double-click the square in the bottom of the cell to copy the formula down the length of the column
        1. Ex. =SUM(I2:J2)
3. Insert a new column called "Exemption Rate"
    1. In the first cell of the new, divide the total number of students who were exempt for that school/year (calculated in the previous step) by the total number of students in each school in each year 
        1. Ex. =K2/E2
    2. Double-click the square in the bottom of the cell to copy the formula down the length of the column, changing for each row (ex. =K3/E3 for row 3)
    4. The formula will produce decimals; re-format the numbers as percentages for easier analysis
4. Sort the "Exemption Rate" column from Z-->A so that the highest exemption rate is at the top
5. Add a filter to the "year" column and select only 2013, 2014, and 2015 (so that the spreadsheet only shows data from those three school years)
6. **_Riverside (100% exemption at Applied Scholastics Academy in 2013-2014), Sacramento (92.86% at Grace Family Christian School in 2014-2015 and 91.67% at Grace Family in 2015-2016), Los Angeles (88.24% at The City School in 2013-2014 and 86.67% at Maple Village Waldorf School in 2013-2014), Alameda (86.96% at Berkeley Rose School in 2014-2015), El Dorado (84.21% at Cedar Springs Waldorf School in 2014-2015)_**
    1. NOTE: All of the exemptions in question were based on beliefs/not for medical reasons, and all of the schools were private with 20 students or fewer
    2. ![Top 5 California Counties with the Highest Exemption Rates at Schools from 2013 and 2015 school years,'5 counties of the schools with the highest exemption rates during the 2013-2014 and 2015-2016 school years'](/Top5.png)
        1. As shown in the table above, the same school in Sacramento County had the highest exemption rate in both 2014 and 2015, though the percentage decreased by 1.19%
        2. The next 5 counties with the schools with the highest exemption rates (not shown in the table or asked about in the question) are Sutter, Nevada, Orange, Mendocino, and Marin (4/5 of which are in Northern California, like Sacramento, Alameda, and El Dorado)

### #7: How did the total number of California kindergarten students with vaccine exemptions change over time, from the 2000-2001 to 2015-2016 school years? Personal belief exemptions?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Create a pivot table from the *entire* dataset to summarize how many kindergarten students overall had vaccine exemptions in 2000 vs. 2015
    1. Add "year" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "year" to the "Filters" section of the pivot table settings and select only 2000 and 2015
    3. Add "n," "Exempted Sum," and "nPBE" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Create a new row below the pivot table titled "Percent Change"
    1. Use the following formula to calculate the percent change in the total number of exemptions and number of personal belief exemptions from the 2000-2001 school year to the 2015-2016 school year (included in the pivot table): =(NEW-OLD)/OLD
        1. Ex. In cell C6, type "=(C3-C2)/C2)" or "=(13679-4390)/4390" then press enter
        2. Ex. In cell D6, type "=(D3-D2)/D2)" or "=(12763-3819)/3819" then press enter
    2. Change the decimals calculated into percentages
4. **_From the 2000-2001 school year to the 2015-2016 school year, the total number of vaccine exemptions increased by 211.59%; the total number of personal belief exemptions increased by 234.2%_**
    1. ![Total Number of Students with Vaccine Exemptions in the 2000-2001 versus the 2015-2016 school years,'screenshot of Google Sheets spreadsheet with total number of exemptions and belief exemptions over time from the 2000-2001 to 2015-2016 school years'](/Question7.png)

### #8: How did the total number of vaccine exemptions for California kindergarten students change from the 2013-2014 to 2015-2016 school years?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Copy the pivot table created for question #7 above to continue analysis about percent change in total vaccine exemption
    1. Keep "year" in the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Keep "year" to the "Filters" section of the pivot table settings but select *2013* and 2015
    3. Add "n" and "Exempted Sum" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Keep the "Percent Change" row below the pivot table (also from question #7 above)
    1. With the formula already entered from the previous question (#7), the percent change should automatically change
        1. Make sure that the formula reads =(NEW-OLD)/OLD so that the number of exemptions in 2013 is subtracted from those in 2015 and all divided by the number of exemptions in 2013
            Ex. =(C3-C2)/C2
4. **_From the 2013-2014 to the 2015-2016 school year, the total number of vaccine exemptions decreased by 21.38%_**
    1. ![Percent change in the number of vaccine exemptions from the 2013-2014 to the 2015-2016 school year,'screenshot of Google Sheets spreadsheet with total number of exemptions from 2013 to 2016'](/ExemptChange.png)

### #9: From the 2013-2014 to 2015-2016 school year, what percentage of kindergartners in each county had vaccine exemptions? What was the percentage breakdown in each county between personal belief exemptions (PBEs) vs. permanent medical exemptions (PMEs)?
1. Use the [StudentData](/StudentData3.xlsx) dataset
2. Create a pivot table from the *entire* dataset to summarize vaccine exemption numbers by county
    1. Add "COUNTY" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "year" to the "Filters" section of the pivot table settings and only select 2013, 2014, and 2015
    3. Add "Exempted Sum" and "n" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Copy the values/non-heading cells into a new sheet to do more non-pivot table analysis
    1. Write the titles for the old headers in the new sheet ("County," "Exempted Sum," "n")
4. Create a new column called "Percent Exempt 2013-16" in the new sheet
    1. In the first cell of the new column, divide the "Exempted Sum" by the "n" in that first row to find the percent of total kindergarten students in the first county who have a vaccine exemption
    2. Drag the square in the bottom right of the cell down to the last county to copy the formula
        1. Check to ensure that the formula changes for each row (ex. =B3/C3 for row 3, =B4/C4 for row 4, etc.)
    3. Change the decimals calculated into percentages
5. ![Kindergartners with personal belief and medical exemptions in each county between 2013 and 2016,'screenshot of Google Sheets spreadsheet with breakdown of exemption types from 2013 to 2016'](/MapShot.png)
    1. NOTE: This question/answer were used in my choropleth map by copying the "Percent Exempt" column into DataWrapper as my "Values" column 
    2. **_The county with the highest overall exemption rate from 2013 to 2016 was Nevada County (20.04%); the county with the lowest overall exemption rate was Sierra County (0%). The average rate of vaccine exemption for California kindergarten students was 4.94%_**
        1. I found these figures by first freezing the top row, then sorting the "Percent Exempt" column in Google Sheets from Z-->A, and then adding a row below the table for "Mean" to calculate the average of the percentages for all 58 counties
6. Create a new pivot table from the dataset to summarize PBE vs. PME numbers by county
    1. Add "COUNTY" to the "Rows" section of the pivot table settings, organized in "ascending order"
    2. Add "year" to the "Filters" section of the pivot table settings and only select 2013, 2014, and 2015
    3. Add "nPBE," "nPME," "n" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
7. Copy the values/non-heading cells into a new sheet to do more non-pivot table analysis
    1. Write the titles for the old headers in the new sheet ("County," "n," "nPBE," and "nPME")
8. Create two new columns called "Percent PBE" and "Percent PME" in the new sheet
    1. In the first cell of the "Percent PBE" column, divide the "nPBE" by the "n" in that first row to find the percent of total kindergarten students in the first county who have a personal belief vaccine exemption
    2. In the first cell of the "Percent PME" column, divide the "nPME" by the "n" in that first row to find the percent of total kindergarten students in the first county who have a personal belief vaccine exemption
    3. Drag the square in the bottom right of these first cells down to the last county to copy the formula
        1. Check to ensure that the formula changes for each row (ex. =C3/B3 for row 3 and =C4/B4 for row 4, etc.)
    4. Change the decimals calculated into percentages
9. ![Kindergartners with Vaccine Exemptions in each county between 2013 and 2016,'screenshot of Google Sheets spreadsheet with total percentage of exemptions from 2013 to 2016'](/MapTooltips.png)
    1. NOTE: This question/answer were used in the tooltips of my choropleth map by copying the "Percent PBE" and "Percent PME" columns into DataWrapper as columns C and D (next to the "Values" column)
    2. **_The highest and lowest personal belief exemption rates occurred in the same counties which had the highest overall exemptions rates (Nevada and Sierra, respectively); the highest medical exemption rate was 0.63% in Plumas County, while the mode PME rate was 0%_**
        1.  I found these figures by first freezing the top row, then sorting the "Percent PBE" and "Percent PME" columns in Google Sheets from Z-->A

### #10: How many California counties had vaccine exemption rates that were higher than the state average, from the 2013-2014 to 2015-2016 school year? How many of these above-average counties are in Northern California?
1. Using the table created and the mean vaccine exemption rate (4.94%) found in part 1 of question set #9 above, sort the "Percent Exempt 2013-16" column from Z-->A to be able to count how many counties had an exemption rate higher than 4.94%
    1. **_23 out of 58 (39.65%) of California counties had overall vaccine exemption rates that were higher than the state average, between 2013 and 2016_**
2. Create a new column called "Northern CA"
    1. Look up each county to determine where it's located and write "TRUE" if it's in the northern half of California (even with the Bay Area or above)
    2. **_Approximately 20 out of the 23 (86.95%) of California counties that have a vaccine exemption rate that is above average (above 4.94%) can be found in the top/northern half of California_**
3. ![Number of counties in California with vaccine exemption rates above the state average between 2013 and 2016,'screenshot of Google Sheets spreadsheet with the counties in 2013-16 that had vaccine exemption rates that were above the state average and whether they're in the northern part of California'](/TopCounties.png)
