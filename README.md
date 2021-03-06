# Scrapy WXR
Scrape training data from https://www.weightxreps.com

## Table of contents
* [General info](#general-info)
* [Setup](#setup)
* [Parsing](#parsing)
* [Status](#status)
* [Inspiration](#inspiration)

## General info
Weightxreps allows you to purchase your own data by donating $5. This is what i recommend when you are interested in your own training data. However i am also interested in training data from others.

## Setup
Create a new virtual environment and install the requirements with ```pip install -r requirements.txt```

## Code Examples
Show examples of usage:
```sh
	scrapy crawl weightxreps
	-a user=[username]
    	-a start=[start date]
      	-a end=[end date]
	-a save_html=[True/False] default is False
        -o [where to save the output]
	-t [format of the result]
```

Date format is YYYY-MM-DD

```sh
# Data by date 2015-09-30
scrapy crawl weightxreps -a user='Bosshogg' -a start='2015-09-30' -a end='2015-09-30' -o /data/Bosshogg/wxr.csv -t csv

# Today's data
scrapy crawl weightxreps -a user='Bosshogg' -a start='today' -o /data/Bosshogg/wxr.csv -t csv
```

If ```save_html=True``` the html files will be saved in ```data/{user_name}/pages/{date}.html```
Pages will only be saved when a training is posted on that date.

## Parsing
Parsing is done via ```xpath``` to parse the html pages.
I use [xpath tester](https://www.freeformatter.com/xpath-tester.html#ad-output) to check my syntax on smaller pieces of html from the wxr source

## Status
Project is: _in progress_, scraping is possible, however i am not getting all the data i want. I want to also add the user's comments

## Inspiration
Fork from https://github.com/linsdev/scrapy-weightxreps
