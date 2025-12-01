# Undestanding-Student-migrations-using-Tableau
A report based on the insights from a Tableau dashboard
## UNDERSTADING INTERNATIONAL STUDENT MIGRATION TO US 

### Introduction
United States continues to be a leading destination for higher education, attracting students from a wide range of socio-economic and cultural backgrounds. Recent political shifts, immigration policy debates, and international tensions have further highlighted the dynamic and sometimes vulnerable nature of student migration. These developments sparked my curiosity to explore the underlying trends and drivers behind the flow of international students to the U.S.
The project investigates few key factors that influence student migration to the U.S from 2022 to 2024 i.e. post COVID era. The objective is to uncover insights that are related to national economic conditions, demographic profiles, and education choices of international students.
The project answers the following research questions:
1.	With respect to population:
a.	How have the international student migration patterns shifted from 2022 to 2024?
b.	Was there a shift in preferred course/level of education and U.S States
2.	How does a country’s GDP related to the number of students migrating to the U.S?
3.	Do students from countries with higher English Proficiency prefer 
a.	certain U.S state or
b.	certain level of education?
4.	Do students from lower Human Development index choose certain programs over others?
5.	Is there a trend between youth unemployment rates and the number of students leaving
a.	for specific degrees?
b.	To certain state?
### Methodology
This project integrates multiple datasets, all joined by country and the corresponding year, to explore international student migration trends and the socio-economic characteristics of their countries of origin. 
 
Figure 1 Data Source

The data source was formed by gathering data from the following sources:
•	SEVIS by the Numbers (2022–2024) — Provides annual records of international students in the U.S., categorized by country, state, gender, and educational program.
Source: https://studyinthestates.dhs.gov/sevis-by-the-numbers/sevis-by-the-numbers-data
•	Population — Includes GDP per capita, unemployment rates, population age distributions, and Human Development Index (HDI).
Source: https://www.census.gov/data-tools/demo/idb/#/pop?dashboard_page=country&COUNTRY_YR_ANIM=2025
•	EF English Proficiency Index — Offers scores measuring adult English proficiency levels by country.
Source: https://www.ef.edu/epi/
•	Unemployment rate by Country — Provides unemployment rates of countries voer the years.
Source: https://databank.worldbank.org/reports.aspx?source=2&series=SL.UEM.TOTL.ZS&country#
•	GDP of countries — Supplies GDP per capita data by each country.
Source: https://www.imf.org/external/datamapper/NGDPDPC@WEO/OEMDC/ADVEC/WEOWORLD
•	Human Development Index — Offere index rating of countries with respect to their HDI.
Source: https://hdr.undp.org/data-center/human-development-index#/indicies/HDI
These datasets varied significantly in structure, frequency, and formatting—ranging from annual student counts to socio-economic indicators like GDP per capita, unemployment rates, and HDI. To prepare the diverse datasets for analysis, I relied heavily on Python, particularly using Pandas and NumPy for data cleaning, transformation, and merging.  Using Pandas, I handled missing values, standardized country names across sources, and performed group-by operations to aggregate values by year or region. For instance, the data procured from the SEVIS website had an aggregated table with count of students in various courses and states in the same table. Pandas allowed me to split the single source of data into two tables specific for courses and states.
Analysis
To explore the research questions, several Tableau charts were created. Below is a breakdown of how each question was addressed:
1.	Migration Patterns based on the population:
a)	Migration Patterns over the years of different countries
It is obvious that countries with large population will have higher number of students migrating to the US. To avoid any misinformation from the skewness, the data was normalized with the entire population of the country and the population of its youth aged between 15-49. The proportions provide a realistic trend of the migration patterns. These calculations were incorporated into the visualizations by using a parameter.
A map highlights the countries with the count or the proportions based on the selection from the parameter. Subsequently, a line chart sketches the values with the corresponding years.
   
A dynamic column chart presents the top 5 countries based on the chosen parameter. A year filter is employed to adjust the entire dashboard along with the above graphs.
b)	Patterns with respect to courses/ level of education and US States
To understand the trends in education, it was also important to understand the patterns in chosen courses or distribution of foreign students in various U.S. states. The year filter was extended to these charts as well. 
 
By using the Total Student Count KPI, we demonstrate the total count of students in the chosen year. This information also aids in understand the spread of students among the states and courses. By using the country map in the dashboard, we can drill down into specific patterns of a country.
2.	GDP per Capita vs. Number of Students
A scatter plot was used to map GDP per capita against the total number of students from each country. This was achieved by using GDP values from the 'GDP for Countries' dataset and student counts from the SEVIS data. Countries were categorized into high-income, upper-middle-income, lower-middle-income, and low-income groups based on their GDP. To analyze the relationship between GDP and student migration on a per-country basis, an animated scatter plot was created to cycle through individual countries, visualizing their GDP alongside the number of students migrating to the U.S.
 
3.	English Proficiency and State/Level of Education Preference
To answer the question whether students from countries with high English proficiency rating choose certain courses or states, a heat map was used to signify the count of students against a course while filtering for countries that have high English Proficiency rating. To extend the analysis, the filter also enables us to filter through low and medium English proficiency too. We leverage maps, to highlight the countries that are categorized by their English proficiency level. This allowed us to enable drilldown on any country within the categories to take a deeper look at the distribution of students among the courses and also identify the preferred state of these students.
 
4.	Human Development as a factor for choosing a level of education or preferred state
Similar to the categorizations based on English proficiency and GDP, countries were grouped by their Human Development Index (HDI) levels. A map visualization was used to highlight countries within each HDI category, enabling quick identification. A pie chart was used to analyze the proportion of students choosing various educational programs within each HDI group. The map also allowed for country-level drilldowns to observe the distribution of chosen education levels for any selected country.
 
5.	Unemployment rates and the number of students opting for a course and a state
A bar graph was chosen to list the count of students choosing a certain course of level of education among countries that are categorized into levels based on the unemployment rate of a country. The categorization also enabled to identify these countries on a map, allowing us to drilldown on any country to understand the choice of course and state among its population.
 

Conclusion
1.	How does a country’s GDP related to the number of students migrating to the U.S?
By considering the proportion of the population migrating to the U.S. for education, countries with low GDP per capita tend to have a lower share of their population choosing to study in the U.S. Interestingly, a similar trend is followed by high GDP per capita countries as well, with only a few outliers showing a notably higher proportion of students studying abroad. While the differences may appear subtle in some cases, there is a higher amount of student migrating to the U.S. from countries with higher GDP.
2.	English Proficiency:
a)	Do students from countries with higher English Proficiency prefer certain U.S. State?
Yes, students from countries with higher English proficiency tend to choose California for their education. One possible explanation is that many institutions in California maintain high academic standards, often requiring strong English language proficiency. Additionally, the higher cost of living in California may be more manageable for students from wealthier, also happen to be high English proficiency countries, making it a more accessible destination for them.
b)	Do students from countries with higher English Proficiency prefer certain courses?
While there is no single chosen course, a majority (41%) of students from countries with high English proficiency opt to pursue various bachelor’s degrees.
3.	Do student form countries with lower HDI choose certain programs over others?
Majority of the countries with low HDI belong the African continent, except Afghanistan and Pakistan. Students from these counties prefer to pursue various Master’s and bachelor’s, while very few are interested in pursuing any other vocational training or language training. This sort of trend is consistent post COVID.
4.	Unemployment rates
a)	Is there a trend between youth unemployment rates and the number of students leaving for certain courses?
Students from countries with high unemployment rates (> 10%) pursue a wide range of courses in US. While majority of them opt for a bachelor’s degree. This trend can be observed to be consistent post COVID. Countries with medium unemployment rates follow a similar trend. A possible explanation for this sort of trend can be explained by the opportunities available in the U.S for an undergrad. In contrast to this, majority of the students from countries with low unemployment rates pursue a master’s degree.
b)	Is there a trend between youth unemployment rates and the number of students leaving to certain states?
New York has the highest percentage of students from countries with high unemployment rates. This could be attributed to the universities present in the state that offer some of the countries most esteemed courses.
While students from countries with low unemployment rates migrate to California to pursue their education.
5.	Population trends
a)	How have the international student migration patterns shifted from 2022 to 2024?
While considering the number of student migrating, the highest count of students migrating to U.S belong to China or India. While China precedes India during 2022 and 2024, there was a rise of almost 90k students migrating from India in 2023. Besides these trends, majority of the students pursue various master programs consistently over the years. While most of the students migrating to California and Texas.
b)	Do countries with the highest number of students migrating to the U.S consistent when normalized?
While India and China consistently top the charts in terms of number of students migrating to the U.S. It isn’t the case when it comes to the overall proportion of its youth. Countries like Dominica, Bahamas, and Bermuda have majority of their population migrating to the U.S to pursue education. This can be attributed to the proximity of these countries to the U.S. 
Beyond answering the research questions, the analysis extends to observe the trens in all sorts of defined metrics. This was possible by using parameters, and filters that allow us to choose different levels of among the factors. An interesting observation that employing these features was how even though certain countries have the highest number of students migrating to the US, they are still a small proportion of the countries population. 
Additional Research questions that originated from the analysis?
1.	Are the trends consistent with Pre COVID era?
2.	Which U.S institutions attract the students from lower HDI or low English proficiency countries?
3.	Do students from lower-income countries tend to enroll in shorter or less expensive programs?



