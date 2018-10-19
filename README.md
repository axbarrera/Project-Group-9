# Quandl Project:<br/>
***

**Members:**<br/> 
Alex Barrera<br/>
Andrew Page<br/>
Shail Shouryya<br/>

## The Ask:<br/>


Before you start writing any code, remember that you only have one week to complete this project. View this project as a typical assignment from work. Imagine a bunch of data came in and you and your team are tasked with migrating it to a production database
Once you have identified your datasets, perform ETL on the data. Make sure to plan and document the following:<br/>
•	The sources of data that you will extract from.<br/>
•	The type of transformation needed for this data (cleaning, joining, filtering, aggregating, etc).<br/>
•	The type of final production database to load the data into (relational or non-relational).<br/>
•	The final tables or collections that will be used in the production database.<br/>

You will be required to submit a final technical report with the above information and steps required to reproduce your ETL process.<br/>

Optional Assignment:<br/>

Visualize the newly transformed data and perform a basic analysis for others to view.<br/>

## Our Finished Products:<br/>

### Our ETL Process:<br/>


Our first step was to find two interesting datasets**. We decided to use investor sentiment data and total energy consumption in the United States. We used monthly data points from 06/1987 through 06/2018. More information about the sets can be found at the bottom of this readme. We then downloaded these datasets as CSV files from quandl.com.<br/>

We then merged our datasets together via pandas. Since each data-set had a different date format we had to create a conversion method to transform the different date-texts into a compatible form. Once this was achieved we left-joined the two data-frames on our newly created column "Date_Index". Next we set about to clean up the dataframe by dropping NAN values and removing unnecessary columns.<br/>

We decided to load our data into a non-relational database (MongoDB). We chose this db since it is still a fairly new tool we have learned about and wanted the practice. Since our data conforms to the formatting standards required by relational databases we could have also used SQL.<br/>

Since MongoDB would be our target database we then set out to convert our pandas dataframes into JSON. From there we wrote a simple script to load the information into MonogoDB.<br/>

Our finished entrey into MongoDB formatted as follows:<br/>

### Visualization:<br/>



##### ** Datasets Used:<br/>
1.<br/>
Investor Sentiment Data from the American Association of Individual Investors
The AAII Investor Sentiment Survey measures the percentage of individual investors who are bullish, bearish, and neutral on the stock market for the next six months; individuals are polled from the ranks of the AAII membership on a weekly basis. Only one vote per member is accepted in each weekly voting period.<br/>
Link: https://www.quandl.com/data/AAII/AAII_SENTIMENT-AAII-Investor-Sentiment-Data<br/>
2.<br/>
Total energy consumption from the U.S. Energy Information Administration
Units: Billion Btu. Total energy consumption, United States <br/>
Link: https://www.quandl.com/data/EIA/SEDS_TETCB_US_A-Total-energy-consumption-United-States<br/>

