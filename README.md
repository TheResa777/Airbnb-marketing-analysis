# <p align = "center"> Airbnb hosts' survival strategies during COVID-19
<p align="center"> Welcome to our journey into the Data World! Join us as we gain insight into the Airbnb survival during COVID-19.
<p align="center"> <img src="https://user-images.githubusercontent.com/98845758/156996224-0fe0db78-1d9d-4869-82bd-6303f97fac72.png" width="700" height="350" >
 
## Research Motivation
The COVID-19 pandemic has been ongoing for almost three years without anyone knowing when it will end and how long the economy can endure. Researchers have gathered emerging evidence of the economic impact of COVID-19 across industries, one of which is the service sector. Due to the contagiousness, social distancing and lockdowns were implemented when COVID-19 dominated in 2020 to 2021. This posed a detrimental challenge to tourism as flights halted in Europe and Asia. When international travel was no longer possible, not only hotels but also Airbnb experienced a plummet by 85% in accommodation occupancy (STR, 2020).

In the discussion of which strategies traditional hotels and Airbnb would deploy in response to disruptive eras like COVID-19, we observe two schools of thought. Studies have found the supply of Airbnb listings fluctuates to meet the seasonal demand, yet the price is inelastic (Zervas et al. 2017, Gunter et al. 2020). This means Airbnb hosts are more flexible in terms of accommodation capacity and availability than traditional hotels. Their listings would be inactive during the off-peak season instead of offering service at a lower price.
 
From a different perspective, due to differences in business nature between traditional hotels and Airbnb, such as anyone can enter the Airbnb market if they have an available property to offer while hotels require a business model covering construction, labor costs to a revenue stream, Airbnb hosts are not entitled to economic support package from the government (ATO, 2020). It is anticipated that Airbnb hosts are likely to decrease lower prices and adjust from short-term to long-term accommodation so that they can manage mortgage payments. Furthermore, how Airbnb hosts deal with pricing during the COVID-19 crisis can be different across the types of accommodation they have.
 
Our study aims to explore how COVID-19 cases as well as other characteristics of Airbnb listings affect the price and to what extent the impact of Airbnb price depends on room types.

## Research Methodology
The analysis is performed on data from Inside Airbnb and European Centre for Disease Prevention and Control (ECDC). Inside Airbnb (insideairbnb.com) is a public website that allows us to freely access web-scraped data on Airbnb listings from every city. Our study focuses on European cities that are available on the website, so some cities may not be covered in the analysis. We downloaded the latest scraped dataset in December 2021 for each analyzed city. Therefore, we specifically selected COVID-19 data reporting the number of confirmed cases up to 2021 so that we could match timestamps between two data sources. Detailed definitions of the analyzed variables are listed below.

| Varible name      | Description |
| ----------- | ----------- |
| year_week| The week number and year of which the data was collected|
| country_code| The 3-letter ISO code  |
|room_type|The room types(Categories:Entire home/apt, Hotel room,Private room, Shared room) |
|avg_price|The average price of the listings|
|minimum_nights|maximum number of night stay for the listing (calendar rules may be different)|
|number_of_reviews|The total number of reviews|
|reviews_per_month|The number of reviews per month|
|calculated_host_listing_count|The number of listings the host has in the current scrape, in the city/region geography |
|availability_365|The availability of the listing x days in the future as determined by the calendar. Note: A listing may not be available because it has been booked by a guest or blocked by the host|
|number_of_reviews_ltm|The number of new listing per quarter|
|weekly_count|The number of covid cases per week| 
|rate_14_day|The 14-day notification rate of reported COVID-19 cases per 100,000 population or 14-day notification rate of reported deaths per 1,000,000 population|
|cumulative_count|The cumulative number of Covid-19 cases|


Since the Airbnb listings dataset is constructed by unique listing IDs, we first created a year-week variable based on the original last review date and time each listing received from guests. Although this matched the format used in the COVID-19 dataset, the deployed technique was restricted to listings that have guest reviews. Moving on to the next stage, we calculated the average price for each year-week combination, city, and room type, hence we were able to isolate outlier observations due to different characteristics of each city and room type. For instance, some cities have way higher living expenses than others, and a whole apartment certainly costs more per night than a private room.

All the analyzed variables except for room types are measured at a continuous scale, for that reason, we implemented a linear regression method. Besides, in line with prior research (Falk et al., 2019, Tang et al., 2019, Sainaghi et al., 2021) we applied logarithm transformation to our response variable. Based on our initial exploration, taking the logarithm of price as part of the remedy to deal with the skewed distribution of price observations. 


## Repository content
This repository contains data on the number of COVID-19 cases per city. Furthermore, it contains Airbnb data from 2021. The data has been collected from various European cities, which include:

* Amsterdam,	Netherlands
* Barcelona,	Spain
* Copenhagen,	Denmark
* London,	United Kingdom
* Madrid,	Spain
* Manchester,	United Kingdom
* Prague,	Czech Republic
* Rome,	Italy
* Thessaloniki,	Greece
* Valencia,	Spain
* Vaud,	Switzerland
* Venice,	Italy
* Vienna,	Austria
* Brussels, Belgium
* Antwerp, Belgium
* Berlin, Germany
* Munich, Germany 


## Our findings
(briefly summarize after analysis report is completed!)



## Running instructions
### Dependencies
* Make [(Installation Guide).](https://tilburgsciencehub.com/get/make)
* R [(Installation Guide).](https://tilburgsciencehub.com/get/r)
* Install R packages: Go to the `code` directory and run the `install_r_packages.R` file  or run it from the command line:  `> Rscript install_r_packages.R`
> Note: Make sure to set the `main` directory as the working directory. This way all required packages will be installed.

### Running the code
Open the command terminal/line:
* Navigate to the `src/analysis` directory. Do this by typing `pwd` for Mac or `dir` for Windows in the terminal.
> Note: If you have issues, type `cd yourpath/` to change your current directory

* Type `make` in the command terminal/line
 
* *Generated files*:

## Repository structure:
```
.
.
├── README.md
├── code
├── data
├── gen
├── src
│   ├── analysis
│   └── data-preparation
├── makefile
└── src.Rproj
```

## Data resources


Visit the data section at [Inside Airbnb](http://insideairbnb.com/get-the-data.html) and [European Centre for Disease Prevention and Control.](https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide)


## About Us

This project was created by Theresa, Vy, and Marissa for the class [Data preparation and Workflow Management (dPrep)](https://dprep.hannesdatta.com/) at Tilburg University.


## References
ATO. (2020). Cash flow boost for Airbnb hosts. ATO: Australian Taxation Office. Retrieved from https://community.ato.gov.au/t5/COVID-19-response/Cash-Flow-Boost-for-Airbnb-Hosts/td-p/76460.
 
Gunter, U., O ̈ nder, I. & Zekan, B. (2020). Modeling airbnb demand to New York city while employing spatial panel data at the listing level. Tourism Management, 77, 104000. http://dx.doi.org/10.1016/j.jclepro.2019.02.221
 
Falk, M., Larpin, B., & Scaglione, M. (2019). The role of specific attributes in determining prices of airbnb listings in rural and urban locations. International Journal of Hospitality Management, 83 (April), 132-140. http://dx.doi.org/10.1016/j.ijhm.2019.04.023.
 
Tang, L.R., Kim, J., & Wang, X. (2019). Estimating spatial effects on peer-to-peer accommodation prices: towards an innovative hedonic model approach. International Journal of Hospitality Management, 81 (March), 43-53. http://dx.doi.org/10.1016/j.ijhm.2019.03.012.
 
Sainaghi. R, Abrate, G., & Mauri, A. Price and RevPAR determinants of Airbnb listings: Convergent and divergent evidence. International Journal of Hospitality Management, 92 (2021). http://dx.doi.org/10.1016/j.ijhm.2020.102709.
 
STR. (2020). STR: Europe hotel performance for April 2020. Retrieved from available at: https://str.com/press-release/str-europe-hotel-performance-april-2020.
 
Zervas, G., Proserpio, D., & Byers, J.W. (2017). The rise of the sharing economy: estimating the impact of airbnb on the hotel industry. Journal of Marketing Research, 54 (5). http://dx.doi.org/10.1509/jmr.15.0204
