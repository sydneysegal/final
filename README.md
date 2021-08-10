# J124 Final Project: *California Kindergarten Immunization Records*

## Story Summary and Sourcing
2014 and 2015 were big years for disease outbreaks in California, especially among children, between a [measles outbreak](https://www.cdc.gov/mmwr/preview/mmwrhtml/mm6406a5.htm) linked to visits to Disneyland theme parks and a [pertussis “epidemic”](https://www.cdc.gov/mmwr/preview/mmwrhtml/mm6348a2.htm). However, since 2000, the rate of vaccine exemption has increased more than two-fold (211.59%). Not only have many parents been [hesitant](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6515949/) to vaccinate their children in recent years, with beliefs that vaccines could cause autism or overwhelm young immune systems, but nonmedical exemptions actually tripled after California banned personal belief exemptions (PBEs) in [2015](https://www.aafp.org/news/health-of-the-public/20181127califvaccstudy.html) in an attempt to increase vaccination rates. Ultimately, this is all to say that a large number of families have objected to vaccinating their children at key moments in public health history –– and especially in Northern California counties (as shown in the data visualization below). While the number of exemptions did decrease slightly during the years in question (21% from 2013 to the end of 2016), **it would be valuable to investigate why there might be a *geographic trend* in vaccine refusal or exemptions**. For example, the higher exemption rates in one area could suggest that there is some sort of urban/rural divide, being higher in smaller and less urban counties. Additionally, the top 7 schools with the highest exemption rates are from within these areas (i.e., Sacramento County is in the northern part of the state). These schools are not necessarily representative of all of Northern California, though they show how vaccination may be linked to values; each school is private, with 20 or fewer students, one school is online, one is religious and made the list twice, etc. 95% of children at a school must be vaccinated to prevent measles transmission, throughout a school or an entire state, but with exemption rates as high as 92.86% from 2013 to the end of 2016 (excluding the online school’s rate of 100%), outbreaks remain possible.

With the help of the three sources below, this story could potentially guide conversation to increase vaccination coverage throughout Northern California –– whether it encourages the intervention of medical professionals or opens families’ eyes to the health risks in their communities. First, **Dr. Richard Pan** (916-262-2904 or 916-651-4006) is a pediatrician and current State Senator representing a majority of Sacramento County. As a doctor and policy maker in Northern California, Pan can provide an expert point of view on the story topic, especially having overseen a number of state bills about vaccine exemptions. For example, Pan’s aforementioned [Senate Bill 277](https://sd06.senate.ca.gov/2015-2016-legislation) abolished personal belief exemptions in 2015 to “ensure that all children can safely attend school.” Second, **Laura Shain** (lshain@lagunitas.org, 415-488-4118 ext. 202) is the principal of two public schools in the Lagunitas School District in Marin County. From the 2013 to 2015 school years, Marin’s overall exemption rate was not the highest but also too high to meet the threshold for “herd immunity,” so it could be valuable to know how Shain feels as a school administrator about being responsible for children who aren’t fully immunized. In a previous [ABC News article](https://abcnews.go.com/Health/inside-anti-vaccine-enclaves/story?id=28693645), she expressed feeling scared about the possibility of a measles outbreak since the school encourages vaccination. Third, **Joshua Nerius** (josh.nerius@servicenow.com) was not vaccinated as a child and contracted measles in 2016. He is based in Chicago and has been previously written about in several national stories, though I believe that he or his parents (two anti-vaxxers) would still be valuable resources to understand the perspective of someone who has been *affected* firsthand by vaccine exemption or to lead me to other potential sources. After all, illnesses are spread the same globally; if one out of three classmates that a child is in contact with isn’t vaccinated, that child is still at risk whether this occurs in California or Illinois.

[“The Effectiveness of California Assembly Bill 2109”](/Effectiveness-CA-Bill-2109.pdf) by Dr. Lilli Goishi-Bessey and 2013-2019 data on [“Kindergartners with All Required Immunizations”](/Kidsdata-All-Required.csv) organized by KidsData.org are two sources that would improve a story on Northern California’s high percentage of vaccine exemptions for kindergartners post-major outbreaks. **First**, Dr. Goishi-Bessey’s work would be helpful because it looks at the 10 most populous counties in California, the same years that my proposed story and visualization do, as well as exemptions *between* the school years (not just at the start of them) and specific reasons for *personal belief exemptions* (i.e., religion or counseling from a Health Care Practitioner). The report pulls from other open access data from the CA Department of Public Health that I could use, though Goishi-Bessey synthesizes it well, especially in relation to state legislation. For example, she links the decrease in PBEs from the 2013 to 2015 school years to the implementation of AB 2109 in 2012 that requires that parents seeking PBEs receive education about vaccine safety. **Second**, since the Kaggle data did not include full immunization rates (I simply estimated how many students were vaccinated against MMR, DTP, and Polio in my data analysis), it would be valuable to look at what percentage of kindergartners have all required immunizations in each California county. While the Kaggle data provided exemption rates, some parents might choose to selectively vaccinate their children based on their beliefs or medical reasoning/not have been exempt from everything. Attached is a CSV file downloaded from KidsData.org, but the KidsData.org [webpage](https://www.kidsdata.org/topic/292/immunizations-kindergarteners/map#loct=3&fmt=63&tf=84&center=-13325098.893387,4509031.392449&zoom=1) presents the data in a choropleth map which shows that Northern California has lower vaccination rates most years to complement its high exemption rates. The KidsData data also includes school district, which would be important to note in my story because there is discrepancy between the schools listed there and in the StudentData CSV file (i.e., the Larkspur-Corte Madera School District does not have its elementary schools listed in the Kaggle data). 

## Data Visualization 
[![Percentage of kindergartners exempt from vaccination in each California county, 2013 to 2015 school years,'The data is presented on a choropleth map of California, with a range of light to dark colors for low to high exemption rates in each county'](/DataViz.png)](https://datawrapper.dwcdn.net/NzQ3v/1/)

## Data Analysis Process

*First, I downloaded the "StudentData.csv," "InfantData.csv" and "pertusisRates2010_2015.csv" files from [Kaggle](https://www.kaggle.com/broach/california-kindergarten-immunization-rates/version/5?select=StudentData.csv) and uploaded them to Google Sheets. Each question below outlines the steps I took to answer it, with the dataset being used marked in step #1 every time. Before beginning the questions, I made sure to "freeze" the top row of columns ("View" tab, then "Freeze," then "1 row"). The questions below build off of one another, so certain steps taken in one question may provide information necessary/referred to in the next.*

### How many California kindergartners got each vaccine each school year?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set to summarize how many students got each vaccine per year
    1. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "nMMR," "nDTP," and "nPolio" to the "Values" section of the pivot table settings, making sure that they are being summarized by "SUM"
        1.  These should appear as columns automatically
    3. Add "year" to the "Filters" section of the pivot table settings and select all but "(Blanks)"
    4. Highlight B2:D18 (the values) and change their format to "number" to produce more readable answers, as **_shown in the screenshot below_**
        1. ![Breakdown of vaccinations by year,'total number of kindergartner MMR DTP and Polio vaccinations by year'](/YearBreakdown.png)
        2. **_Most notable from the answers above is that the highest number of students were vaccinated against MMR, DTP, and Polio in 2015 (517k, 516k, and 518k, respectively); the second-highest number of students for all three vaccinations occurred in 2000 (497k, 497k, and 500k), the first school year that the data was recorded_**

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
    1. ![Approximate Number of Fully Vaccinated CA Kindergartners from 2000 to 2015,'Google Sheets table of vaccination breakdown for California kindergartners in 2000 and 2015 with percent fully vaccinated based on lowest number for individual vaccines'](/FullVax.png)

### Which California county had the most infant Pertussis cases in 2014? Highest case rate? Highest death rate?
1. Use InfantData.csv in Google Sheets
2. Sort "Cases" column from Z-->A to organize the counties with the most infant Pertussis cases at the top
3. **_Los Angeles had 143 Pertussis cases in 2014, only 1 of which died_**
    1. ![Top 5 California Counties With Most Infant Pertussis Cases in 2014,'Los Angeles County had the most pertussis cases in infants in 2014](/InfantCases.png)
5. Sort "Case Rate" column from Z-->A to show the counties with the most Pertussis cases per 1,000 infants at the top
6. **_Madera County had the highest case rate for infants with Pertussis in 2014 (6.1 per 1,000 infants), with just 7 cases total_**
7. ![Top 5 California Counties With Highest Infant Pertussis Case Rates in 2014,'Google Sheets screenshot of InfantData.csv file sorted by highest to lowest case rate'](/InfantRate.png)
8. Sort "County" column from A-->Z to return to original file set-up
9. Add a title to Column F: "DEATH RATE"
    1. In cell F2, write the formula =D2/B2 (divides the number of deaths by the number of cases)
    2. Drag the square in the bottom of the cell to the bottom of the column (row 59) to copy the formula down the length of the column
        1. Make sure that the formula has changed by row for each cell, D3/B3 for row 3, D4/B4 for row 4, etc.
    3. Delete the contents of any cells in which the #DIV/0! error appears (these counties had 0 Pertussis cases in 2014)
    4. Format the remaining decimals as percentages
    5. To find the highest death rate, sort column F from Z-->A
10. **_Placer County had the highest infant death rate of 33.33% in 2014 (1 in 3 cases died); only 4 counties had any deaths (1 each for Santa Barbara, Joaquin, and Los Angeles too)_**
    1. ![Infant Death Rate by Pertussis in 2014 in the Top 5 California Counties,'Google Sheets table of the top 5 California counties with the highest death rates of infants with pertussis in 2014'](/InfantDeath.png)

### Which California county had the highest rate of Pertussis cases in 2014? How does this county compare to the county with the most infant Pertussis cases in 2014 (found above)?
1. Use pertusisRates2010_2015.csv in Google Sheets
2. Freeze the first column of the sheet so that the county names stay in place when scrolling to distant columns/cases and rates can be easily compared against the counties
3. Sort the "Rate 2014" column from Z-->A to reveal the highest rates at the top of the spreadsheet
4. **_Sonoma County had the highest rate of Pertussis cases in 2014 (142.18 per 100,000 people); although Los Angeles had the most infant Pertussis cases in 2014 (2.1 per 1,000 infants according to Kaggle and included in the table above), the county only had 20.25 cases per 100,000 people in 2014_**
    1. **_Comparing just the Los Angeles figures, Los Angeles County had 10 times as many Pertussis cases in infants than they did the whole population in 2014 (2.1 cases per 1,000 infants is equivalent to 210 cases per 100,000 infants)_**
    2. ![California County with Most Pertussis cases versus Los Angeles in 2014,'Sonoma County had the highest rate of Pertussis cases in 2014 at 142.18 per 100k people and Los Angeles had only 20.25 per 100k people'](/PertussisRates.png)

### Between the 2000 and 2015 school years, were more California kindergartners exempt from vaccinations in public or private schools? What percentage of kindergartners in each school type were exempt based on beliefs vs. medical reasons?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set
    1. Add "schoolType" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "n," "nPBE," and "nPME" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Create a new sheet
    1. Copy and paste all of the white cells from the pivot table into this new sheet, leaving room for new headers
    2. Write the titles for the old headers in the new sheet (school type, n, nPBE, nPME)
4. Insert a column to the right of "nPME" titled "Sum Exempt" (column E)
    1. Write the following formula in cell E2 and hit enter: =SUM(C2:D2)
    2. Double click the quare in the bottom right of cell E2 to copy the formula down the column: =SUM(C3:D3) and =SUM(C4"D4), respectively
5. Insert a column to the right of "Sum Exempt" titled "Percent Exempt" (column F)
    1. In cell F2, divide the contents of cell E2 by B2 for the percent of of kindergartners with exemptions in private schools (=E2/B2, then press enter)
    2. In cell F3, divide the contents of cell E3 by B3 for the percent of kindergartners with exemptions in public schools (=E3/B3, then press enter)
    3. Format the decimals as percentages
6. **_3.23% of total private school kindergartners were exempt from vaccinations from the 2000 to 2015 school years; 1.81% of total public school kindergartners were exempt from vaccinations_**
7. Insert a new column to the right of "Percent Exempt" titled "Percent Belief" (column G)
    1. In cell G2, divide the contents of cell C2 by E2 (number of private school kindergartners exempt for beliefs by the total number of private school kindergartners exempt)
    2. In cell G3, divide the contents of cell C3 by E3 (number of public school kindergartners exempt for beliefs by the total number of public school kindergartners exempt)
8. **_93.21% of private school kindergartners in California who were exempt from their vaccinations between the 2000 and 2015 school years had "personal belief exemptions"; 91.38% of exempted public school kindergartners were exempt based on beliefs"_**
    1. ![Vaccination Exemptions by School Type,'summary statistics of vaccination exemptions in public and private schools in California from 2000 to 2015'](/SchoolType.png)

### List the 5 counties (of the schools) with the highest exemption rates during the 2013-2014, 2014-2015, and 2015-2016 school years.
1. Use StudentData.csv in Google Sheets
2. Insert a new column to the right of column J (becomes the new column K), titled "Exempted Sum"
    1. In the first cell of column K (K2), write the formula =SUM(I2:J2) to take the sum of students exempt from vaccinations for belief *and* medical reasons, then double-click the square in the bottom of the cell to copy the formula down the length of the column 
3. Insert a new column to the right of the "Exempted Sum" column (becomes the new column L) titled "Exemption Rate"
    1. In the first cell of column L (L2), write the formula =K2/E2, column E being "n" (the total number of students in each school in each year) and column K being the total number of students who were exempt for that school/year (calculated in the previous step)
    2. Double-click the square in the bottom of the cell to copy the formula down the length of the column, changing for each row (i.e., =K3/E3 for row 3)
    3. The formula will produce decimals; re-format the numbers as percentages for easier analysis
4. Sort column L ("Exemption Rate") from Z to A so that the highest exemption rate is at the top
5. Add a filter to column M ("year") and select only 2013, 2014, and 2015 (so that the spreadsheet only shows data from those three school years)
6. **_Riverside (100% exemption at Applied Scholastics Academy in 2013), Sacramento (92.86% at Grace Family Christian School in 2014 and 91.67% in 2015), Los Angeles (88.24% at The City School in 2013 and 86.67% at Maple Village Waldorf School in 2013), Alameda (86.96% at Berkeley Rose School in 2014), El Dorado (84.21% at Cedar Springs Waldorf School in 2014_**
    1. NOTE: All of the exemptions in question were based on beliefs/not for medical reasons, and all of the schools were private with 20 students or fewer
    2. ![Top 5 California Counties with the Highest Exemption Rates at Schools from 2013 and 2015 school years,'5 counties of the schools with the highest exemption rates during the 2013-2014 and 2015-2016 school years'](/Top5.png)
        1. As shown in the table above, the same school in Sacramento County had the highest exemption rate in both 2014 and 2015, though the percentage decreased by 1.19%
        2. The next 5 counties with the schools with the highest exemption rates (not shown in the table or asked about in the question) are Sutter, Nevada, Orange, Mendocino, and Marin (4/5 of which are in Northern California, like Sacramento, Alameda, and El Dorado)

### How did the total number of California kindergarten students with vaccine exemptions change over time, from 2000 to 2015? Personal belief exemptions?
1. Use StudentData.csv in Google Sheets
2. Create a pivot table from the *entire* data set
    1. Add "year" to the "Rows" section of the pivot table settings and select "ascending order"
    2. Add "year" to the "Filters" section of the pivot table settings and select only 2000 and 2015
    3. Add "n," "Exempted Sum," and "nPBE" to the "Values" section of the pivot table settings, making sure that they are summarized by "SUM"
3. Create a new row below the pivot titled "Percent Change" (type in cell A6)
    1. Use the following formula to calculate the percent change in the total number of exemptions and number of personal belief exemptions from the 2000 school year to the 2015 school year: =(NEW-OLD)/OLD
        1. In cell C6, type "=(C3-C2)/C2)" or "=(13679-4390)/4390" then press enter
        2. In cell D6, type "=(D3-D2)/D2)" or "=(12763-3819)/3819" then press enter
    2. Change the decimals calculated into percentages
4. **_From the 2000-2001 school year to the 2015-2016 school year, the total number of vaccination exemptions increased by 211.59%; the total number of personal belief exemptions increased by 234.2%_**
    1. ![Total Number of Students with Vaccine Exemptions 2000 versus 2015,'screenshot of Google Sheets spreadsheet with total number of exemptions and belief exemptions over time from 2000 and 2015'](/ExemptChange.png)
