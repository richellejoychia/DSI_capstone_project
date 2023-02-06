# Travel Recommender System Based on Activity Preferences

Done by: Richelle-Joy Chia, [Linkedin](https://www.linkedin.com/in/richelle-joy-chia/)

## **Notebooks**

- 01 Introduction and Data Acquisition
- 02 Data Cleaning and EDA
- 03 Feature Engineering and Recommender System
- 04 NLP - Sentiment Analysis on Reviews
- 05 Streamlit


## **Background**

The time and effort involved in planning a vacation sometimes go unaccounted for as there are way too many information online to sieve through. Hence, the goal of this project is to build a recommender system that would evaluate the overwhelming number of POIs and provide personalized recommendations to users based on their preferences. A content-based recommendation system is proposed, one that uses information about the user's preferences and POIs to calculate a degree of similarity between them. In other words, it selects POIs, which have highest similarity with the user's preferences, to recommend to users. 

## **Problem statement**

Existing systems rarely aim at recommending tangible itineraries for tourists within a specific POI due to the difficulty of acquiring information about the true user behavior, that is, the sequence of experiences that travelers perform. While their online information search activity is easy to be tracked, their true experiences, that is, the POIs they visit, are only known indirectly, in the form of selected reviews, which only specific travelers would usually provide. This is much different from other domains, such as Netflix, where the user's watching behavior is easily tracked and users can experience their "like" for a movie by just one click.

## **Libraries and packages used**

- pandas
- numpy
- scipy
- matplotlib
- selenium
- seaborn
- plotly
- scikit-learn
- regex
- transformers
- tqdm
- pickle
- flask
- json

## **Data Acquisition** 

1. Part 1 of the data (e.g., attraction name, url, reviews, country, price, ratings) was retrieved from a group of people who worked on a travel recommender system. [Click here to refer to source.](http://localhost:8888/files/Capstone%20files/%5Bhttps%3A/github.com/sachinnpraburaj/Intelligent-Travel-Recommendation-System/tree/master/outputs%5D(https%3A/github.com/sachinnpraburaj/Intelligent-Travel-Recommendation-System/tree/master/outputs)?_xsrf=2%7Cb41084ba%7C04a82f1fb2c7dd7f3784b231db96d008%7C1668645866)
2. Part 2 of the data (e.g., images, duration, and description) was scraped from TripAdvisor using Selenium. The images and duration were scraped to showcase on Streamlit. As for the description, it was partially used to create the labels based on a Hugging Face model. This was not included in Streamlit as I wanted to only show information that would capture people's attention instantly.

## **Feature engineering**

1. Combined the columns that are related to each other - based on feedback from user testing 
2. Presence/absence of ratings and reviews - mostly from users who are on extreme ends of satisfaction 
3. Weighted ratings - input mean and scaled the ratings 

## **Evaluating the recommender system and findings**

1. The content-based recommender system was built using Cosine Similarity, which is one of the most popular techniques used in recommendation systems. The attributes used were the hand-labelled categories. The intuition behind this sort of recommendation system is that if a user liked a particular type of activity, he/she might like a similar activity.
2. After coming up with the base model, I created a survey and did A/B testing as well as User Acceptance Testing (UAT) to see if users are pleased with the recommendations.

## **Limitations and future work**

Even though the results of the recommender system were satisfactory, more can be done to improve this recommender system and the web deployment.

- The activities included were only in Canada and may not be as comprehensive. It would be interesting to scrap data from other countries and incorporate it into the recommender system such that users who like a particular attraction would be recommended attractions from other countries as well.
- Only cosine similarity was used in building this recommender systemm. Future work can collect implicit feedback that are not ratings or scores provided by the user, such as clicks and participated activities. Thereafter, a hybrid recommender system can be implemented.
- The data is still somewhat limited for a recommender system and future work can continue to collect more information from users to improve recommendations.
- The NLP Hugging Face model is only used for category labelling. It would be interesting to create weights with the results and see whether positive, negative, or neutral emotions would influence the results.

As for the Streamlit deployment,

- It is best viewed on desktop due to the layout, which may not be convenient for most users. One possible solution would be to deploy this on a mobile app for easy access.
- The radio button may not be the most intuitive for users to rate. Afterwhich, I would like to create a swipe function such that users can swipe the photo either right (like) or left (dislike) to indicate their preferences. Having a bigger button would suffice as well. These steps would allow smoother and more instantaneous response.
- The filter on the sidebar is still a work in progress and future work can improve the future to ensure that when users click on the fliter, the filtered activities will follow suit.
- Currently, there is only 1 emotion label that is being shown. It may be useful to incoporate more than 1. Moreover, future work can use different huggingface models to explore other labels.
- Only 1 photo is being displayed and this photo may not be the most accurate. As such, it would be interesting to explore more photos or even short videos/reels in future.

## **External resources**

- [Google sheets for labelling of categories](https://docs.google.com/spreadsheets/d/1SdWfaTsiF70kirT-8QC4Cq97O_T2ZBc_8tnWh0fTmCo/edit?usp=sharing)
- [Qualtrics link for survey testing](https://ntuhss.az1.qualtrics.com/jfe/form/SV_0GIxdDgBGg9L7kG)
- [Streamlit App](https://richellejoychia-streamlit-apps-streamlit-app-akwx1q.streamlit.app/)
