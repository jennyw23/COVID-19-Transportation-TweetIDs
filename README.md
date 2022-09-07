# COVID-19-Transportation-TweetIDs

The repository contains a collection of tweet IDs related to mobility and transportation during the coronavirus pandemic. It scrapes tweets from the [COVID-19-TweetIDs dataset](https://github.com/echen102/COVID-19-TweetIDs/tree/master/2022-03) in order to capture tweets which mention specific keywords. To comply with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), we only release the Tweet IDs of the collected COVID-19+Transportation Tweets. 

The associated paper to this repository can be found here: 

For further background, the associated paper to the COVID-19-TweetIDS repository can be found here: [Tracking Social Media Discourse About the COVID-19 Pandemic: Development of a Public Coronavirus Twitter Data Set](https://publichealth.jmir.org/2020/2/e19273/)


## Data Organization
The Tweet-IDs are organized as follows:
* Tweet-ID files are stored in folders that indicate the year and month of the collection (YEAR-MONTH). 
* Individual Tweet-ID files contain a collection of Tweet IDs, and the file names all follow the same structure, with a prefix “covid-mobility-tweet-” followed by the YEAR-MONTH-DATE. 

Template: `covid-mobility-tweet-YYYY-MM-DD.txt`
Example: `covid-mobility-tweet-2021-07-30.txt`


## Notes About the Data

### Data Collection Notebooks
Access the notebooks used for data collection here: [COVID-19-Transportation](https://github.com/jennyw23/COVID-19-Transportation)

### COVID-19+Transportation Data Collected
    
The COVID-19+Transportation Dataset collects data with the following steps:
- open a COVID-19 tweet file
- run through the tweet IDs within the file
    - rehydrate the tweet
    - search for transportation keywords based on a predetermined list
    - if a transportation keyword is found, add it to the list. Otherwise, move on to the next tweet
    - when either (1) the file end is reached or (2) the list of COVID-19+Transportation tweets exceeds 1000, we save the tweets in a `.jsonl` file.
    
As of 4/9/2022, I have set up `nohup` to run on several threads in order to collect data from various date ranges. I have obtained relevant data from 1/22/2020 - 1/25/2020. The scripts are currently collecting from the following 6 date ranges on the Wellesley CS Server:
- 3/11/2020 - 3/27/2020
- 3/28/2020 - 5/1/2020
- 5/2/2020 - 5/8/2020
- 7/23/2020 - 8/30/2020
- 11/24/2020 - 11/31/2020
- 12/11/2020 - 12/25/2020
    
Until 4/26/2022, I was also running over 60 processes on a computer in Knapp Library. This allowed for an increased volume of tweets from a greater range of dates.
