# (WeRateDogs twitter data)
## by (Oni Sodiq Adesola)


## Dataset

The data consists of information regarding 2356 Dogs data from **WeRateDogs** twitter account, including retweet_count, favourite_count, and other features. The dataset can be found [here] (https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv), (https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv), (https://video.udacity-data.com/topher/2018/November/5be5fb7d_tweet-json/tweet-json.txt).


## Summary of Findings

The wrangling process is divided into three stages:


1. Gathering: The data used for this project was gathered from three different sources. The data and their sources are;
        
* twitter_achieved_enhanced.csv: This file was given by the udacity team and I downloaded it manually using this link here https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv, I then read and upload the data as twitter_data to pandas DataFrame. The file contains the tweet_id, names, ratings, retweet status, dog types etc.
* image_prediction.tsv: The file is present in each tweet according to a neural network. It is hosted on Udacity's servers and I downloaded it programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv, I then read it into Pandas DataFrame as image_prediction.
            
* tweet_json.txt: I was unable to create a twitter developer account so i make use of the tweet json file provided by udacity, Then I read this tweet_json.txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count as tweet_data.

2. Assessing: After gathering all three pieces of data, I assessed them visually and programmatically for quality and tidiness issues. Each piece of gathered data was displayed in the Jupyter Notebook for visual assessment. Microsoft excel was also used in accessing the gathered data visually. Pandas functions were also used in assessing the datas programmatically. The following are the quality and tidiness issues detected in the data;
        
### Quality issues
        
#### twitter_data table
        
* tweet_id is not string

* timestamp is not datetime

* invalid dog names such as just, all, none, a, the, this, very, such, an, by, his, my, not

* zero denominator in row 313

* missing data in in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp

#### image_prediction
* missing photos for some tweet IDs

* some names start with capital letters while others with small letters

#### tweet_data
* missing data in id, retweet_count, favorite_count

### Tidiness issues
* id column instead on tweet_id in tweet_table

* dog types separated in different columnns
   
    
3. Cleaning: The detected quality and tidiness issues were cleaned accordingly to enhance the quality of the data for analyzing and visualization.


## Key Insights 

1. I looked at the relationship between Dog types and retweet count using sum plot. Pupper has the highest retweet counts while Floofer has the lowest retweet counts. 

2. I also checked for relationship between dog types and favourite count. I used the mean favourite count to plot a bar chart for eact dog types, Floofer has the highest mean favourite count while Pupper has the lowest mean favourite counts.

3. Lastly, I checked for relationship between Dog types and ratings using pie chart, Doggo has the highest average rating while Puppo has the lowest average rating.


