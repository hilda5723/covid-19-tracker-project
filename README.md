# covid-19-tracker-project

# COVID-19 Global Data Tracker

## 📜 Project Description

This project involves building a data analysis and reporting notebook to track global COVID-19 trends. It analyzes cases, deaths, and vaccinations across countries and time, using real-world data primarily sourced from Our World in Data (OWID). The project emphasizes a full data analysis workflow: data acquisition, cleaning, processing, exploratory data analysis (EDA), insight generation, and the visualization of trends using Python and its associated data science libraries.

The final output is a well-documented Jupyter Notebook (`.ipynb`) that combines Python code, generated visualizations (charts, maps), and narrative explanations of the findings.

## 🚩 Project Objectives

*   ✅ **Import and Clean Data:** Load the global COVID-19 dataset and perform necessary cleaning steps, such as handling missing values and converting data types.
*   ✅ **Time Trend Analysis:** Analyze and visualize how key metrics (total cases, total deaths, new cases, new deaths, total vaccinations, etc.) have evolved over time for selected countries or globally.
*   ✅ **Cross-Country Comparison:** Compare COVID-19 metrics (e.g., cases per million, death rates, vaccination rates) across different countries and regions to identify patterns and disparities.
*   ✅ **Effective Visualization:** Utilize `matplotlib`, `seaborn`, and `plotly` to create informative line charts, bar charts, and choropleth maps that clearly communicate trends and comparisons.
*   ✅ **Insight Communication:** Summarize key findings, anomalies, and interesting patterns observed from the data analysis within the Jupyter Notebook using markdown cells.

## 📊 Data Source and Codebook

The primary dataset used for this project is **`owid-covid-data.csv`**, provided by Our World in Data. This comprehensive dataset aggregates COVID-19 statistics from various official sources worldwide.

A detailed description of each column within `owid-covid-data.csv` is available in the **`owid-covid-codebook.csv`**. The content of this codebook is essential for understanding the nuances of each data field.

### Key Columns Utilized in this Analysis (selected from codebook):

*   **`iso_code`**: ISO 3166-1 alpha-3 – three-letter country codes.
*   **`continent`**: Continent of the geographical location.
*   **`location`**: Geographical location (country or region name).
*   **`date`**: Date of observation.
*   **`total_cases`**: Total confirmed cases of COVID-19.
*   **`new_cases`**: New confirmed cases of COVID-19.
*   **`new_cases_smoothed`**: New confirmed cases of COVID-19 (7-day smoothed).
*   **`total_deaths`**: Total deaths attributed to COVID-19.
*   **`new_deaths`**: New deaths attributed to COVID-19.
*   **`new_deaths_smoothed`**: New deaths attributed to COVID-19 (7-day smoothed).
*   **`total_cases_per_million`**: Total confirmed cases per 1,000,000 people.
*   **`total_deaths_per_million`**: Total deaths per 1,000,000 people.
*   **`population`**: Population of the location (used for per-capita calculations).
*   **`total_vaccinations`**: Total number of COVID-19 vaccination doses administered.
*   **`people_vaccinated`**: Total number of people who received at least one vaccine dose.
*   **`people_fully_vaccinated`**: Total number of people who received all doses prescribed by the initial vaccination protocol.
*   **`people_fully_vaccinated_per_hundred`**: People fully vaccinated per 100 people in the total population.
*   **`new_vaccinations_smoothed`**: New COVID-19 vaccination doses administered (7-day smoothed).

### Full Data Codebook (from `owid-covid-codebook.csv`)

<details>
<summary>Click to expand and view the full data dictionary</summary>

```csv
column,source,category,description
iso_code,International Organization for Standardization,Others,ISO 3166-1 alpha-3 – three-letter country codes. Note that OWID-defined regions (e.g. continents like 'Europe') contain prefix 'OWID_'.
continent,Our World in Data,Others,Continent of the geographical location
location,Our World in Data,Others,Geographical location
date,Our World in Data,Others,Date of observation
total_cases,COVID-19 Dashboard by the WHO,Confirmed cases,"Total confirmed cases of COVID-19. Counts can include probable cases, where reported."
new_cases,COVID-19 Dashboard by the WHO,Confirmed cases,"New confirmed cases of COVID-19. Counts can include probable cases, where reported. In rare cases where our source reports a negative daily change due to a data correction, we set this metric to NA."
new_cases_smoothed,COVID-19 Dashboard by the WHO,Confirmed cases,"New confirmed cases of COVID-19 (7-day smoothed). Counts can include probable cases, where reported."
total_deaths,COVID-19 Dashboard by the WHO,Confirmed deaths,"Total deaths attributed to COVID-19. Counts can include probable deaths, where reported."
new_deaths,COVID-19 Dashboard by the WHO,Confirmed deaths,"New deaths attributed to COVID-19. Counts can include probable deaths, where reported. In rare cases where our source reports a negative daily change due to a data correction, we set this metric to NA."
new_deaths_smoothed,COVID-19 Dashboard by the WHO,Confirmed deaths,"New deaths attributed to COVID-19 (7-day smoothed). Counts can include probable deaths, where reported."
total_cases_per_million,COVID-19 Dashboard by the WHO,Confirmed cases,"Total confirmed cases of COVID-19 per 1,000,000 people. Counts can include probable cases, where reported."
new_cases_per_million,COVID-19 Dashboard by the WHO,Confirmed cases,"New confirmed cases of COVID-19 per 1,000,000 people. Counts can include probable cases, where reported."
new_cases_smoothed_per_million,COVID-19 Dashboard by the WHO,Confirmed cases,"New confirmed cases of COVID-19 (7-day smoothed) per 1,000,000 people. Counts can include probable cases, where reported."
total_deaths_per_million,COVID-19 Dashboard by the WHO,Confirmed deaths,"Total deaths attributed to COVID-19 per 1,000,000 people. Counts can include probable deaths, where reported."
new_deaths_per_million,COVID-19 Dashboard by the WHO,Confirmed deaths,"New deaths attributed to COVID-19 per 1,000,000 people. Counts can include probable deaths, where reported."
new_deaths_smoothed_per_million,COVID-19 Dashboard by the WHO,Confirmed deaths,"New deaths attributed to COVID-19 (7-day smoothed) per 1,000,000 people. Counts can include probable deaths, where reported."
reproduction_rate,Arroyo Marioli et al. (2020). https://doi.org/10.2139/ssrn.3581633,Reproduction rate,Real-time estimate of the effective reproduction rate (R) of COVID-19. See https://github.com/crondonm/TrackingR/tree/main/Estimates-Database
icu_patients,"National government reports and European CDC",Hospital & ICU,Number of COVID-19 patients in intensive care units (ICUs) on a given day
icu_patients_per_million,"National government reports and European CDC",Hospital & ICU,"Number of COVID-19 patients in intensive care units (ICUs) on a given day per 1,000,000 people"
hosp_patients,"National government reports and European CDC",Hospital & ICU,Number of COVID-19 patients in hospital on a given day
hosp_patients_per_million,"National government reports and European CDC",Hospital & ICU,"Number of COVID-19 patients in hospital on a given day per 1,000,000 people"
weekly_icu_admissions,"National government reports and European CDC",Hospital & ICU,Number of COVID-19 patients newly admitted to intensive care units (ICUs) in a given week (reporting date and the preceeding 6 days)
weekly_icu_admissions_per_million,"National government reports and European CDC",Hospital & ICU,"Number of COVID-19 patients newly admitted to intensive care units (ICUs) in a given week per 1,000,000 people (reporting date and the preceeding 6 days)"
weekly_hosp_admissions,"National government reports and European CDC",Hospital & ICU,Number of COVID-19 patients newly admitted to hospitals in a given week (reporting date and the preceeding 6 days)
weekly_hosp_admissions_per_million,"National government reports and European CDC",Hospital & ICU,"Number of COVID-19 patients newly admitted to hospitals in a given week per 1,000,000 people (reporting date and the preceeding 6 days)"
total_tests,National government reports,Tests & positivity,Total tests for COVID-19
new_tests,National government reports,Tests & positivity,New tests for COVID-19 (only calculated for consecutive days)
total_tests_per_thousand,National government reports,Tests & positivity,"Total tests for COVID-19 per 1,000 people"
new_tests_per_thousand,National government reports,Tests & positivity,"New tests for COVID-19 per 1,000 people"
new_tests_smoothed,National government reports,Tests & positivity,"New tests for COVID-19 (7-day smoothed). For countries that don't report testing data on a daily basis, we assume that testing changed equally on a daily basis over any periods in which no data was reported. This produces a complete series of daily figures, which is then averaged over a rolling 7-day window"
new_tests_smoothed_per_thousand,National government reports,Tests & positivity,"New tests for COVID-19 (7-day smoothed) per 1,000 people"
positive_rate,National government reports,Tests & positivity,"The share of COVID-19 tests that are positive, given as a rolling 7-day average (this is the inverse of tests_per_case)"
tests_per_case,National government reports,Tests & positivity,"Tests conducted per new confirmed case of COVID-19, given as a rolling 7-day average (this is the inverse of positive_rate)"
tests_units,National government reports,Tests & positivity,"Units used by the location to report its testing data. A country file can't contain mixed units. All metrics concerning testing data use the specified test unit. Valid units are 'people tested' (number of people tested), 'tests performed' (number of tests performed. a single person can be tested more than once in a given day) and 'samples tested' (number of samples tested. In some cases, more than one sample may be required to perform a given test.)"
total_vaccinations,National government reports,Vaccinations,Total number of COVID-19 vaccination doses administered
people_vaccinated,National government reports,Vaccinations,Total number of people who received at least one vaccine dose
people_fully_vaccinated,National government reports,Vaccinations,Total number of people who received all doses prescribed by the initial vaccination protocol
total_boosters,National government reports,Vaccinations,Total number of COVID-19 vaccination booster doses administered (doses administered beyond the number prescribed by the vaccination protocol)
new_vaccinations,National government reports,Vaccinations,New COVID-19 vaccination doses administered (only calculated for consecutive days)
new_vaccinations_smoothed,National government reports,Vaccinations,"New COVID-19 vaccination doses administered (7-day smoothed). For countries that don't report vaccination data on a daily basis, we assume that vaccination changed equally on a daily basis over any periods in which no data was reported. This produces a complete series of daily figures, which is then averaged over a rolling 7-day window"
total_vaccinations_per_hundred,National government reports,Vaccinations,Total number of COVID-19 vaccination doses administered per 100 people in the total population
people_vaccinated_per_hundred,National government reports,Vaccinations,Total number of people who received at least one vaccine dose per 100 people in the total population
people_fully_vaccinated_per_hundred,National government reports,Vaccinations,Total number of people who received all doses prescribed by the initial vaccination protocol per 100 people in the total population
total_boosters_per_hundred,National government reports,Vaccinations,Total number of COVID-19 vaccination booster doses administered per 100 people in the total population
new_vaccinations_smoothed_per_million,National government reports,Vaccinations,"New COVID-19 vaccination doses administered (7-day smoothed) per 1,000,000 people in the total population"
new_people_vaccinated_smoothed,National government reports,Vaccinations,"Daily number of people receiving their first vaccine dose (7-day smoothed)"
new_people_vaccinated_smoothed_per_hundred,National government reports,Vaccinations,"Daily number of people receiving their first vaccine dose (7-day smoothed) per 100 people in the total population"
stringency_index,"Oxford COVID-19 Government Response Tracker, Blavatnik School of Government",Policy responses,"Government Response Stringency Index: composite measure based on 9 response indicators including school closures, workplace closures, and travel bans, rescaled to a value from 0 to 100 (100 = strictest response)"
population,"United Nations, Department of Economic and Social Affairs, Population Division, World Population Prospects 2019 Revision",Others,"Population (latest available values). See https://github.com/owid/covid-19-data/blob/master/scripts/input/un/population_latest.csv for full list of sources"
population_density,"World Bank World Development Indicators, sourced from Food and Agriculture Organization and World Bank estimates",Others,"Number of people divided by land area, measured in square kilometers, most recent year available"
median_age,"UN Population Division, World Population Prospects, 2017 Revision",Others,"Median age of the population, UN projection for 2020"
aged_65_older,World Bank World Development Indicators based on age/sex distributions of United Nations World Population Prospects 2017 Revision,Others,"Share of the population that is 65 years and older, most recent year available"
aged_70_older,"United Nations, Department of Economic and Social Affairs, Population Division (2017), World Population Prospects 2017 Revision",Others,Share of the population that is 70 years and older in 2015
gdp_per_capita,"World Bank World Development Indicators, source from World Bank, International Comparison Program database",Others,"Gross domestic product at purchasing power parity (constant 2011 international dollars), most recent year available"
extreme_poverty,"World Bank World Development Indicators, sourced from World Bank Development Research Group",Others,"Share of the population living in extreme poverty, most recent year available since 2010"
cardiovasc_death_rate,"Global Burden of Disease Collaborative Network, Global Burden of Disease Study 2017 Results",Others,"Death rate from cardiovascular disease in 2017 (annual number of deaths per 100,000 people)"
diabetes_prevalence,"World Bank World Development Indicators, sourced from International Diabetes Federation, Diabetes Atlas",Others,Diabetes prevalence (% of population aged 20 to 79) in 2017
female_smokers,"World Bank World Development Indicators, sourced from World Health Organization, Global Health Observatory Data Repository",Others,"Share of women who smoke, most recent year available"
male_smokers,"World Bank World Development Indicators, sourced from World Health Organization, Global Health Observatory Data Repository",Others,"Share of men who smoke, most recent year available"
handwashing_facilities,United Nations Statistics Division,Others,"Share of the population with basic handwashing facilities on premises, most recent year available"
hospital_beds_per_thousand,"OECD, Eurostat, World Bank, national government records and other sources",Others,"Hospital beds per 1,000 people, most recent year available since 2010"
life_expectancy,"James C. Riley, Clio Infra, United Nations Population Division",Others,Life expectancy at birth in 2019
human_development_index,United Nations Development Programme (UNDP),Others,"A composite index measuring average achievement in three basic dimensions of human development—a long and healthy life, knowledge and a decent standard of living. Values for 2019, imported from http://hdr.undp.org/en/indicators/137506"
excess_mortality,"Human Mortality Database (2021), World Mortality Dataset (2021)",Excess mortality,"Percentage difference between the reported number of weekly or monthly deaths in 2020–2021 and the projected number of deaths for the same period based on previous years. For more information, see https://github.com/owid/covid-19-data/tree/master/public/data/excess_mortality"
excess_mortality_cumulative,"Human Mortality Database (2021), World Mortality Dataset (2021)",Excess mortality,"Percentage difference between the cumulative number of deaths since 1 January 2020 and the cumulative projected deaths for the same period based on previous years. For more information, see https://github.com/owid/covid-19-data/tree/master/public/data/excess_mortality"
excess_mortality_cumulative_absolute,"Human Mortality Database (2021), World Mortality Dataset (2021)",Excess mortality,"Cumulative difference between the reported number of deaths since 1 January 2020 and the projected number of deaths for the same period based on previous years. For more information, see https://github.com/owid/covid-19-data/tree/master/public/data/excess_mortality"
excess_mortality_cumulative_per_million,"Human Mortality Database (2021), World Mortality Dataset (2021)",Excess mortality,"Cumulative difference between the reported number of deaths since 1 January 2020 and the projected number of deaths for the same period based on previous years, per million people. For more information, see https://github.com/owid/covid-19-data/tree/master/public/data/excess_mortality"