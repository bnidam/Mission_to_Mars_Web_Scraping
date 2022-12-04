![The planet Mars](https://github.com/bnidam/Mission_to_Mars_Web_Scraping/blob/main/Resources/Mars.png) image from WorldAtlas https://www.worldatlas.com/space/why-is-mars-so-small.html

# Mission_to_Mars_Web_Scraping

## Overview of Project
Websites are full of information - from headline news and insteresting articles to data. Web-scraping is a useful way to extract that information or data to compile and analyze it. This project uses a variety of tools to practice all of these skills.

### Purpose
The purpose of this project is to use web scraping to collect information and data, format and organize this information and/or data, and analyze it to answer questions, then store those files. This project aids in the practice of identifying HTML elements and their attributes, extracting and parsing various types of information - text, links, data.

### Tools
This project uses Python and jupyter notebooks with the following imports: Splinter, Beautiful Soup, ChromeDriverManager to extract several types of information and data from websites and files, and pandas, numpy, matplotlib, json to organize, format, analyze and store. 

## Analysis 

### Part 1
The first part of this project involved creating a compilation of headline news about Mars from the Mars News website https://redplanetscience.com/.  The compilation contains the title and preview text of the articles scraped from that website, put into Python dictionary format, and saved as a JSON file named XXXXXXXXXXXXX.

### Part 2
The second part of this project involved scraping data from an html file on aws (Mars Temperature Data https://data-class-mars-challenge.s3.amazonaws.com/Mars/index.html). The scraped data was put into a Pandas DataFrame, reformatted to data types appropriate to the data in each column, and then analyzed to answer the five questions listed below. The answers are shown below. The analysis process and answers are also available in the code of the mars_data_challenge_part_2.ipynb.

#### How many months exist on Mars?
- This is a tricky question as the term "Month" is an Earth-oriented term referring to the time that it takes for our Moon to go one full cycle around the Earth. Mars has 2 very small moons, named Phobos and Deimos, and neither of them lend themselves very well for a "Martian Month" cycle comparable to our concept of "a month".
- For the data that scraped from the html file, there are 12 unqiue numbers shown in the column titled "month". 

#### How many Martian (and not Earth) days worth of data exist in the scraped data?
- By counting the unique number of "sol" values in the data, there are 1867 Martian days worth of data in the dataset. 

#### What are the coldest and the warmest month on Mars (at the location of Curiosity)?
- The dataset months 3 and 4 are tied for the coldest months on Mars with an average temperature of -83 degrees Celcius.
- The dataset month 7 is the warmest month on Mars with an average temperature of -68 degrees Celcius. 

Below is a bar graph showing the average minimum temperatures pr month on Mars from the dataset.
![Bar chart: Average Miinimum Temperatures by Month](https://github.com/bnidam/Mission_to_Mars_Web_Scraping/blob/main/Resources/Avg_Min_Temp_Month.png)

#### Which months have the lowest and the highest atmospheric pressure on Mars?
- The dataset month 6 has the lowest atmospheric pressure with an average atmospheric pressure of 745.05.
- The dataset month 9 has the highest atmospheric pressure with an average atmospheric pressure of 913.31.
- Note: the dataset does not disclose the unit of measure for atmospheric pressure. Assuming from the temperature degress reported in Celcius, I could assume that this is reported in Pascals but it could be millibars. I chose to not give a unit of measure.

Below is a bar graph showing the average daily atmospheric pressure per month on Mars from the dataset.
![Bar chart: Average Atmospheric Pressure by Month](https://github.com/bnidam/Mission_to_Mars_Web_Scraping/blob/main/Resources/Avg_Atmos_Press_Month.png)

#### About how many terrestrial (Earth) days exist in a Martian year? 
- By starting with the solar longitude of Curiosity's first record, noting the number of sols in the dataset with that same solar longitude and the Earth date of those particular sols, then counting the sols in between those dates, there are approximately 686 Earth days in a Martian year.
- This calculation was confirmed by plotting the daily minimum temperature for all the data in the dataset and then estimating the number of sols between points of apparent seasonal fluctuation: lowest points to lowest points, highest points to highest points. The chart showing the daily minimum temperatures is below.
![chart: Daily Minimum Temperatures](https://github.com/bnidam/Mission_to_Mars_Web_Scraping/blob/main/Resources/Daily_Min_Temp.png)