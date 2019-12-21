### Team: Neha Anna John, Rawini Dias, Chris Henson, Sadhana Koneni, Satya Naren Pachigolla

# Customer Brand Preferences using MDS Plots:

In this case we are analytics consultants to a (i) brand manager, (ii) product manager and (iii) advertising manager. Our job is to give advice/insights to these individuals based on the analysis of social media conversations. We use cars as an example of a “high involvement” good (recall from class discussions that for high involvement goods, people use social media heavily for awareness building and research). 

## Process

1) Extract the messages from a general car consumer forum using 'Selenium'

2) Calculate the number of co-mentions between different brands and plot the lift values in a MDS plot

3) Create a list of key attributes the consumers are discussing about by looking at the discussions

4) Look into how all of the brands are mentioned together to each of these attributes and identify specific patterns if any

5) Using our insights from this analysis, we make recommendations to different people on areas of improvement and provide awareness about competitors


# Tracking Instagram Engagement using Topic Modelling:

#### Is a Picture Worth a Thousand Words?
On Instagram, we choose the National Geographic (natgeo) page. Wrote a scraper to extract (i) image URLs (do not extract video URLs, it may end up costing you a lot of money to run analytics on video), (ii) post caption (the text description of a post), (iii) # likes and (iv) # comments. 

Using the image URLs, obtained image labels from Google Vision cloud (you will have to create an account with Google to get your credentials as a json file, though the first $300 are free, which should be more than plenty for this case).

Created a metric for engagement by using a weighted sum of # likes and # comments. However, we first normalized # likes and # comments such that they both have values between 0 and 1. You can scale the # likes by dividing by the maximum # likes (for a post) in your data and do the same for # comments, so that # likes and comments will be in the range [0,1]. Now created an engagement score = .4*# likes (normalized) + .6*# comments (normalized). Defined High (1) and Low (0) engagement based on whether the engagement score is above or below the median value.  

Our job is to give advice to National Geographic if it wants to increase engagement on its Instagram page based on your findings 

## Process

1) Extract image URLs, number of likes, comments and the captions assosciated with them from Instagram

2) Cretead an 'Engagement Score' using the likes and comments count. Defined each image as 'High Engagement' or 'Low Engagement'

3) Using Google Vision, got the tags for each of the images

4) Did topic modelling for the image tags, image captions and combination of both. 

5) Using Logistic Regression on the different topic weights, we tried to predict the Engagement Score of the pictures
