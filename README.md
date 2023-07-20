

# Power Outages and Socioeconomics

### Welcome!!

This README will guide you through the stages of this project, and by the end we will have explored data about power outages, how weather affects energy access, charted populations that are dependent on medical equipment who are especially reliant on energy access. We will come away with skills to explore data using Python and Pandas, and identified correlations both using visual plots and statistical tests.

## Teeing up the Problem

In June of 2016, a heatwave swept across the SW United States, causing severe loads on the power grid, and leading to large number of power outages across several counties. We are going to be exploring correlations between temperature and power outages, and the level of exposure these effects have on medically vulnerable populations.

Energy justice in the United States means making sure that people have access to energy and are also not being charged disproportionately for the basic energy services that are standardly provided. An energy burden is the fraction of a person’s income that goes toward paying for their electrical power. For populations that are medically vulnerable - reliant on medication or medical equipment for day to day life, their energy burden is higher due to the additional costs in maintaining medical care cutting into available income to pay for power. The populations that are reliant on electrically dependent medical equipment (DMEs) are also especially vulnerable during power loss as there is an immediate risk to health to these populations. 

The ability to effectively respond to and facilitate the restoration of energy systems during disasters relies on the ability of local and federal agencies and first responders to have timely, accurate, and actionable information about the status and potential impacts of energy sector disruptions. The US Department of Energy (DOE) provides information about these disruptions via its Environment for Analysis of Geo-Located Energy Information (EAGLE-I) system run by Oak Ridge National Laboratory. EAGLE-I provides capabilities for monitoring energy infrastructure assets, reporting energy outages, and displaying potential threats to energy infrastructure, and coordinating emergency response and recovery.

We will be building tools to explore data to understand where medically vulnerable populations are located (particularly those dependent on medical equipment, called DME) and how significantly they were affected during the 2016 heatwave.  

You will be focusing primarily on the US states California, Nevada, and Arizona in the June 17-24, 2016 time period. We have datasets with resolution at the county level. One gives the monthly breakdown for the year 2016 of the number of people registered with Medicare and registered as relying on a DME. There is another set that shows how may customer were without power in 15-minute intervals from 2015-2021. We have a other set that tracks the June 2016 heat wave temperatures that we will be using to explore what happens to energy justice when the power grid is under stress.

### EAGLE-I Background

EAGLE-I is the US Department of Energy’s data and information platform for real-time wide-area situational awareness of the energy sector, sponsored by the DOE Office of Cybersecurity, Energy Security, and Emergency Response. It is developed and run from Oak Ridge National Laboratory in Tennessee. 

The EAGLE-I system allows local, state, and federal government agencies, and private sector electricity and fuel providers to have access to timely, accurate, and actionable information about the status and potential impacts of energy sector disruptions and provides a modernized framework for the next set of capabilities in emergency response support.

Developed by the Office of Electricity Delivery and Energy Reliability’s (OE) Infrastructure Security and Energy Restoration (ISER) division, EAGLE-I uses data science approaches to provide a centralized platform for monitoring power distribution outages for over 133 million customers, with just over 90% coverage of the US and Territories. Oak Ridge National Laboratory provides EAGLE-I as a service to other Federal, State, and local agencies and departments and first responders aligning with DOE’s Emergency Support Function-12 (ESF-12) mission, and users come from DOE, DHS, NGA, DOD, FEMA, USDA, and state emergency responders, among others.



## TODO: Setup instructions
Instructions for how to copy the project repo from NERSC CFS location to individual group project directory.



### Datasets

All the data we need is in this google drive folder: https://drive.google.com/drive/folders/1fAaBPgWWaA_9VB2iYUAWeW8biTXJQFwZ?usp=sharing and also will be stored on the NERSC file system so you can easily copy it. 

For the Python notebook exercises, you will need to copy the data from (TODO nersc CFS location) into the data folder in this directory on the NERSC Jupyter.

We are going to be working with four main datasets:

* eaglei_outages/eaglei_outages_2016.csv - provides the breakdown of the number of customers that were out of power in the year 2016, for each county in the US, with data for each 15 minute increment covering the entire year. The eaglei_outages directory also has csv files for other years. You can use them to explore power outage data for others if you're so inclined! NOTE: the timestamp is in UTC+0 so you will need to adjust the time stamp according to the time zone of the location you're looking at.


* temperaturedata/CtyAvTempMDDYY.csv - in the temperaturedata folder, each .csv file is the average temperature of the day for each county in the US and its territories. The numbers in the file name represent the date. For example CtyAvTemp61716.csv is the data for June 17 2016.

* 2016_HHSemPOWERMapHistoricalDataset.xlsx - data of population across US counties registered with Medicare, also including size of the population relying on DMEs for the year 2016 Broken down by month. You can see an interactive map here: https://empowerprogram.hhs.gov/empowermap (You can also get datasets for years other than 2016 if you're interested in exploring that later. See here: https://empowerprogram.hhs.gov/about-empowermap.html).


* NOTE: Something you'll find as you work with these datasets is that there might be some data missing here and there e.g. There might not be power outage information for some county for some given day. That's just the nature of data science sometimes, that the data you have isn't perfect. So you have to make sure that you're using the data you have and making sure you're accounting for any missing data when before you make any conclusions. You may need to use Excel or your favorite method to "Clean" some of the data sets. Cleaning is the process of removing problematic data, such as ASCII letters or punctuation characters that appear where numbers should be, or reformatting one set of data, so it can be compared to another set.


### Jupyter Notebooks

The exercises and tutorials linked below are in Jupyter notebooks and will familiarize you with the provided data and prepare you to answer the the big questions.
1. Link 1 - Exploring the datasets - Explore the datasets that you will be working with Google Sheets, draw some graphs
    1. Who should do this? All group members
2. Link 2 - Python and Pandas intro - Some refresher material from Kellen's Python and Pandas tutorial. Along with using Python and Pandas to explore our datasets and learning some useful Pandas tools you'll need for working with these datasets.
    1. Who should do this? All group members
3. Link 3 - Time series data - Exploring the EAGLE-I time series dataset, including looking at grouping and aggregation, and how to use aggregated data with other regular data with Pandas.
    1. Who should do this? At least one group member
4. Link 4 - Correlation and Causation - Learn how to calculate the correlation between two data points. A useful statistical technique to learn when working with data where plots don't show any obvious correlation/plots would be an inconvenient representation. 
    1. Who should do this? At least one group member.
5. Link 5 - Drawing Maps - Learn how to draw maps and lay your data on a map.
    1. Who should do this? At least one group member.
6. Link 6 - Big Questions - Use this notebook to work on answering the big questions.
    1. Who should do this? The group working together.


## The Big Questions for this Project:

These are the questions you will be trying to answer using the data you have been given and the skills you developed during the bootcamp and by going through the material in the Jupyter Notebooks. Unless stated otherwise, focus on the counties in the states California, Nevada, and Arizona (but feel free to explore other states too if you're curious once your done answering the questions for those states!). Use the notebook 6_Answering_Big_Questions.ipynb to work on your answers (you can split the work up between the group by making a copy of the notebook for each member, or work on it together in the same notebook). 

1. Which counties in the Southwest US were hit with the highest average temperatures in June 17-24, 2016? Can you show it visually, one chart for each day showing the top X counties? (Datasets: CtyAvTemp6XY16.csv where XY is 17,18,19,...,24)

2. Of the counties in the SW United States, for June 2016, which counties had the highest and lowest DME reliant population? What percentage of the total population of the county is that? Can you show the top X counties for each? (Datasets:  2016_HHSemPOWERMapHistoricalDataset.xlsx)

3. Can you show the average number of customers without power per county during the heatwave? Can you show it visually, one chart for each day showing the top X counties? (Data sets: eaglei_outages_2016.csv) 
    1. To show how the power outage numbers during a heatwave differ from days when there wasn't a heatwave, can you determine what the average number of customers without power per county is during a time period there wasn't a heatwave? And can you include that information in your charts?
    
4. Can you generate a map showing, for a given day, the counties with the highest temperatures along with their average power outage size for that day, and the size of the DME reliant population of that county? (Datasets: eaglei_outages_2016.csv, CtyAvTemp6XY16.csv where XY is 17,18,19,...,24, 2016_HHSemPOWERMapHistoricalDataset.xlsx)


5. Given what we saw for many of these power outages and the populations that might be affected, what recommendations would you make for readiness for heatwaves: a. for local emergency services b. to the county government c. to the state and federal government

You are doing super well if you get through question 5! The rest of the questions are stretch goals. Feel free to do any of them that you find interesting.  

6.  Can you tell if the number of customers without power is correlated with the highest temperatures of a particular day during the heatwave? Pick a county or a few counties to make it simpler. (Datasets: eaglei_outages_2016.csv and  search the internet for hourly temperature information for that particular day. You may even have to make your own dataframe with the hourly temperature information if you want to use Pandas to identify the correlation. Here's an example resource that shows hourly temperatures: https://www.timeanddate.com/weather/usa/los-angeles/historic?month=6&year=2016016/historic?month=6&year=20166&year=2016).
    1. You may have to use interpolation to potentially fill in missing data.

7. Can you identify if there is a correlation between the size of the medically vulnerable populations and the size of the asthmatic population? (Datasets: 2016_HHSemPOWERMapHistoricalDataset.xlsx and CtyAvDemog2010.csv . Note that the CtyAvDemog2010.csv is data from 2010. Make sure you are considering that caveat when you present the results.)
    1. Are you able to investigate if there is a correlation between the size of the medically vulnerable populations and anything else in the CtyAvDemog2010.csv data? What have you tried to investigate? And what did it show you? 

8. Look for data on the internet about another natural disaster that happened between 2015 and 2021 and see if you can repeat the analysis for it. How many customers lost power? How exposed were the medically vulnerable populations in those counties? examine the power outage information from the data in eaglei_outages from among the years we have available data for. 
  
9. Try submitting a couple of jobs to the Perlmutter supercomputer. See the 6_Answering_Big_Questions.ipynb for more info and instructions.

**Note** You do not have to tackle the Big Questions with the exercises given in this guide if you have another plan in mind to work with. These are here to help you get started and are not mandatory.


### The Final Product:

You will combine your visualizations and insights from answering the big questions into a presentation that you will give on the last day of the workshop.


### Goals:

* Discuss access to electrical power to medically vulnerable populations and the size of those populations affected during power outages
* Understand how to use statistical tests to justify correlations.
* Understand how to create and use visualizations to show connections and correlations in big data.
* Utilize Python and Excel to explore large data frames.
* Discuss how doing tasks in parallel is more efficient than doing them in series.
* Present your analyses to the judges in the presentation and explain the assumptions you made in your analyses. For example, if you use “total customers” for a given region to represent relative total populations between counties, acknowledge that while the members of one household are all counted as one customer and businesses are a customer too, "total customers" is still a measure of relative size of the populations of customers living in each county.


## Some reading resources:

* Map of burdened communities: https://screeningtool.geoplatform.gov/en
* Articles about the 2016 heatwave:
* https://web.archive.org/web/20160622004100/
* https://weather.com/forecast/regional/news/dangerous-record-heat-southwest-plains
* https://www.huffpost.com/entry/record-heat-wildfires-west-us_n_57678bb4e4b015db1bc9be59?section=
* Medicare at risk population map: https://empowerprogram.hhs.gov/empowermap
* FIPS Codes - https://en.wikipedia.org/wiki/List_of_United_States_FIPS_codes_by_county
* Useful Jupyter examples for this project - https://github.com/secondspass/jupyter_bootcampproject_examples/
* Pandas tutorial - https://www.activestate.com/resources/quick-reads/what-is-pandas-in-python-everything-you-need-to-know/
* Nice visualization of past temperature information - https://www.timeanddate.com/weather/usa/los-angeles/historic?month=6&year=2016016/historic?month=6&year=20166&year=2016
* Example of interactive notebook that use government data (on Google Colab) -  https://www.environmentalenforcementwatch.org/data/notebooks



## Acknowledgements
* Data and scientific inspiration and guidance for this project was developed by ORNL Scientists Melissa Dumas and Sarah Tennille.
