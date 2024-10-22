# Disneyland Reviews Analysis Report

**Executive Summary**

This project aims to identify customer sentiment regarding Disneyland experience based on reviews from visitors. The reviews are from TripAdvisor about three Disneyland branch locations: California, Paris, and Hong Kong. Through performing Exploratory Data Analysis (EDA), monthly review trends analysis, branch-specific comparisons, and polarity-based sentiment analysis, I evaluated visitors’ sentiment on their experience in each Disneyland branch and identified their potential pain points, empowering Disneyland to enhance consumer experiences.

**1. Data Overview**

I used the dataset found in [Kaggle](https://www.kaggle.com/datasets/arushchillar/disneyland-reviews/data) containing 42,656 reviews from TripAdvisor. Variables’ descriptions are provided below:
- Review_ID: unique id given to each review
- Rating: ranging from 1 (unsatisfied) to 5 (satisfied)
- Year_Month: when the reviewer visited the theme park
- Reviewer_Location: country of origin of visitor
- Review_Text: comments made by visitor
- Disneyland_Branch: location of Disneyland Park

When performing data preprocessing and cleaning before the analysis, I discovered that there are duplicates Review_Text within the same Review_ID. To ensure each review is unique, I removed those duplicates and kept the first occurrence. The dataset was left with 42,644 records. Year_month column consists of 6% missing values out of total records. Since the goal is to analyze the reviews, these values are not dropped because removing these missing dates will result in loss of data.

To make it computationally easier, I decided to split up the data by branch location to analyze smaller samples (Figure 1).

![image](https://github.com/user-attachments/assets/2d480792-19dd-44b3-840d-5db2d9f04f85)

                      (Figure 1. Number of Reviews for the Three Disneyland Branches)

Among three branches, California has the highest percentage of review (approximately 46%). Paris ranked the 2nd, and Hong Kong the last.

**2. Key Findings and Insights**

**2.1 Disneyland Experience Satisfaction (Figure 2, 3, 4)**

In general, a majority of visitors had a satisfying experience at Disneyland parks. Only 3.52% of visitors indicated that they have unsatisfying experience at Disneyland parks, rating their experience with 1 star. While there is a high proportion of 4-star and 5-star ratings, there is still room for improvement to shift more lower-star experiences to 4 and 5 stars experiences. Future strategy would be to investigate factors leading to 4-star reviews and implement targeted improvements to enhance visitor experiences.

Looking at the rating distribution by branches, Disneyland California consistently performs the best with the highest number of 5-star ratings compared to the other branches. Disneyland California also has the highest average star rating among three branches, indicating it provides the most satisfactory consumer experience. Paris falls below the 4-star average threshold, suggesting there may be operational challenges or room for improvement in visitor experience. We should conduct research studies on Paris Disneyland. This could involve surveys or analyzing review text to uncover specific challenges, such as crowding, service issues, or facilities.

![image](https://github.com/user-attachments/assets/44d41c9d-6636-46fb-b1ad-0a1cd1d8e422)
      
                          (Figure 2. Distribution of Ratings in %)

![image](https://github.com/user-attachments/assets/731e6e9e-3057-4831-9262-7deb041d25d5)

                    (Figure 3. Distribution of Ratings by Disneyland Branch)

![image](https://github.com/user-attachments/assets/7a3c6214-fd2e-4486-b4e7-6e51db2efb62)

                        (Figure 4. Average Rating by Branch)

**2.2 Sentiment Analysis (Figure 5, 6, 7)**

Sentiment analysis is the process of determining the attitude or the emotion of the review, i.e., whether it is positive or negative or neutral. In this section I will take a closer look into the reviews to reveal visitor sentiment.

The method used here is TextBlod, which measures two key aspects - Polarity and Subjectivity. Polarity tells us whether the review is positive, negative, or neutral. Subjectivity measures how much of the review is based on personal opinion rather than factual information. Based on the polarity score, reviews are labeled as Positive (Polarity > 0), Negative (Polarity < 0), or Neutral (Polarity = 0). The result is shown below (Figure 5).

Overall, all three parks have a high frequency of “positive” reviews. However, to have a better idea of why some consumers had an unpleasant park experience, I took a closer look at the negative reviews.

![image](https://github.com/user-attachments/assets/f5adcbfe-369c-4524-b8ed-4b7701a0fa29)

                          (Figure 5. Review Sentiment by Branch)

**2.2.1 Words in Negative Reviews (Figure 6, 7)**

By taking a closer look at the negative reviews in words related to time (Figure 6), making visitors wait about one hour or more tends to drive them to write negative reviews. Terms like “night” and “evening” suggest that visitors may have experienced challenges with events or services late in the day, such as long queues or limited staff availability.

Negative reviews in terms of people's names (Figure 7) shows "Peter Pan" and "Mickey Mouse" are frequently mentioned, suggesting that negative experiences happened when taking the Peter Pan ride and interacting with Mickey Mouse-themed attractions. The word “didn” (likely part of “didn’t”) suggests unmet expectations, such as attractions or services not functioning as expected.

To enhance consumer experience at Disneyland, we should review operations at popular attractions like Peter Pan and Mickey Mouse-themed attractions to ensure smooth in-park experiences. In addition, continuous monitoring of queue times and the implementation of real-time feedback systems will help manage consumer expectations effectively in the waiting line. Following a 3 to 6-month period of implementation, conducting sentiment analysis on reviews again or targeted surveys will provide valuable insights to assess the effectiveness of these measures and determine whether further strategic adjustments are required to optimize the consumer experience.

![image](https://github.com/user-attachments/assets/580e80f1-1f02-42a5-b1ea-5c386da6cca3)

                  (Figure 6. Time Words in Negative Reviews)

![image](https://github.com/user-attachments/assets/af68f0f8-07a8-466f-a5f7-a5a6546e7b42)

                (Figure 7. People Name Words in Negative Reviews)


**2.3 Peak Time to Visit Disneyland (Figure 8, 9)**

Each Disneyland branch exhibits unique monthly visitor patterns, likely influenced by regional holidays and seasonal events (Figure 8). For the Hong Kong branch, the peak period is December, which is aligned with the Christmas and Chinese New Year holiday season. For the California branch,the peak periods are less distinguished compared to the Hong Kong branch. Visitor numbers remain high from June to September, indicating that the park experiences steady traffic throughout the summer, aligning with summer vacations in the United States. While January and February are quieter months, it’s actually making sense as California’s weather is cold and windy in these months. It’s more enjoyable to visit resort parks in the summer. The Paris branch has the highest number of reviews in August, which correlates with summer vacation in Europe. When I grouped the months into quarters, quarter 3 becomes the busiest period to visit Disneyland for all the Disneyland branches (Figure 9).

The analysis of visitors flow gives us great insight on traffic management and resource planning. For months during holiday periods, such as December in Hong Kong, summer in California and August in Paris, the parks need additional resources and staff to maintain customer satisfaction and avoid negative reviews caused by long wait times or overcrowding. All parks have clear off-peak months, for example, February and January, Disneyland can use this time for maintenance or introduce off-season discounts to attract more consumers. Promoting off-season discounts on off-peak months to loyal consumers might be a good strategy to build consumer loyalty as less overcrowded parks would give them better in-park experiences.

![image](https://github.com/user-attachments/assets/580d9338-00b5-4ae6-80bb-8f4f57953862)

                  (Figure 8. Peak Time to Visit Disneyland by Months)

![image](https://github.com/user-attachments/assets/1633df74-30a7-45df-ab96-a59d74e72d60)

                  (Figure 9. Peak time to Visit Disneyland by Quarters)


**2.4 Major Groups Visiting Disneyland Branches (Figure 10)**

Compared to Hong Kong and Paris branches, California Disneyland attracts more local consumers. While for Hong Kong and Paris branches, the park draws more international attention compared to local’s. For future opportunities, California Disneyland can enhance engagement with local visitors while also offering special deals to Australian and Canadian tourists to build repeat visits. Hong Kong Disneyland should focus on retaining visitors from Australia and India. It’s interesting that the majority of reviews for Hong Kong Disneyland didn’t come from the local residents as it is considered as a signature of Hong Kong. One potential reason could be local residents are not used to leaving reviews on Tripadvisor. For Paris Disneyland, strengthening its relationship with UK and US visitors through loyalty programs and holiday packages would be beneficial. 

![image](https://github.com/user-attachments/assets/795a8387-4384-41b6-8937-765a53fbc3c7)

              (Figure 10. Major Groups Visiting Disneyland Branches)

**Conclusion**

This report highlights consumer insights from consumer reviews across Disneyland branches in California, Paris, and Hong Kong. The analysis reveals overall positive consumer review sentiment, with California Disneyland providing the most satisfactory experiences. However, there are still areas for potential enhancement, especially in addressing operational inefficiencies and customer service issues.

Key actions to take for improvement opportunities include:
- **Operational Enhancements:**
    - Disneyland California, Paris, Hong Kong: Investigate factors leading to 4-star reviews and implement targeted improvements to enhance visitor experiences.
    - Disneyland Paris: Conduct research studies on Paris Disneyland to analyze why average rating is below 4-star. It can involve surveys or analyzing review text to uncover specific challenges, such as crowding, service issues, or facilities.
- **Attraction-Specific Improvements:**
    - Reviewing operations at popular attractions like Peter Pan and Mickey Mouse-themed attractions
    - Implementing real-time feedback systems on waiting time for better queue management.
- **Traffic Management and Off-Peak Strategies:**
    - Ensuring adequate staffing and resources during peak periods (e.g., summer in California, December in Hong Kong, and August in Paris) to maintain consumer satisfaction
    - Promoting off-season discounts and introducing loyalty programs during quieter months to help maintain steady visitor traffic, building consumer loyalty and providing better experiences during less crowded times.
- **Sentiment Tracking and Continuous Monitoring:**
    - Implementing follow-up sentiment analysis or surveys 3 to 6 months after operational changes, assessing the effectiveness of new strategies and providing ongoing insights for improvement.

