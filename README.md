Exp-No---6---Sentiment-Analysis-of-Product-Reviews-Using-TextBlob







Aim:




To load product review text, perform sentiment analysis using TextBlob, classify reviews as positive, negative, or neutral, and count the results.





Algorithm:





1. Import Libraries – Import TextBlob from the textblob package.

  
2. Create Sample Reviews – Define a list of product review strings.


3. Initialize Counters – Keep counters for positive, negative, and neutral reviews.



4. Perform Sentiment Analysis:



   - For each review, compute sentiment.polarity (range: -1 → negative, +1 → positive).
  

   - Categorize review based on polarity value.
  

5. Count and Display Results – Show sentiment category for each review and total count summary.




6. Visualize (optional) – Use a simple bar chart to show sentiment distribution.



Program:

   # Sentiment Analysis on Product Reviews using TextBlob

from textblob import TextBlob

import matplotlib.pyplot as plt

# Step 1: Create a list of sample product reviews

reviews = [


   
    "The product is amazing and works perfectly!",

    "Very disappointed with the battery life.",

    "Quality is okay but could be improved.",

    "Absolutely fantastic! Exceeded my expectations.",

    "Not worth the price at all.",

    "Packaging was good and delivery was on time.",

    "The screen resolution is poor and camera is bad.",

    "Loved the design and the features offered.",

    "Average product, nothing special.",

    "Excellent performance and great value for money!"

]

# Step 2: Initialize counters

positive = 0

negative = 0

neutral = 0

# Step 3: Analyze sentiment for each review

print("---- Sentiment Analysis Results ----")

for review in reviews:

    analysis = TextBlob(review)

    polarity = analysis.sentiment.polarity

    if polarity > 0.1:

        sentiment = "Positive"

        positive += 1

    elif polarity < -0.1:

        sentiment = "Negative"

        negative += 1

    else:

        sentiment = "Neutral"

        neutral += 1

    print(f"Review: {review}")

    print(f"Polarity: {round(polarity, 2)} | Sentiment: {sentiment}\n")

# Step 4: Display summary

print("---- Summary ----")

print("Positive Reviews:", positive)

print("Negative Reviews:", negative)

print("Neutral Reviews:", neutral)

# Step 5: Plot sentiment distribution

labels = ['Positive', 'Negative', 'Neutral']

values = [positive, negative, neutral]

plt.figure(figsize=(6,4))

plt.bar(labels, values, color=['green', 'red', 'blue'])

plt.title("Sentiment Distribution of Product Reviews")

plt.xlabel("Sentiment Type")

plt.ylabel("Number of Reviews")

plt.show()






output:



 ---- Sentiment Analysis Results ----

 
Review: The product is amazing and works perfectly!


Polarity: 0.8 | Sentiment: Positive

Review: Very disappointed with the battery life.


Polarity: -0.98 | Sentiment: Negative

Review: Quality is okay but could be improved.


Polarity: 0.5 | Sentiment: Positive

Review: Absolutely fantastic! Exceeded my expectations.



Polarity: 0.5 | Sentiment: Positive

Review: Not worth the price at all.


Polarity: -0.15 | Sentiment: Negative

Review: Packaging was good and delivery was on time.


Polarity: 0.7 | Sentiment: Positive

Review: The screen resolution is poor and camera is bad.


Polarity: -0.55 | Sentiment: Negative

Review: Loved the design and the features offered.


Polarity: 0.7 | Sentiment: Positive

Review: Average product, nothing special.


Polarity: 0.1 | Sentiment: Positive

Review: Excellent performance and great value for money!


Polarity: 1.0 | Sentiment: Positive

---- Summary ----


Positive Reviews: 7


Negative Reviews: 3


Neutral Reviews: 0

<img width="532" height="389" alt="Screenshot 2026-11-20 140257" src="https://github.com/user-attachments/assets/fa9801d4-1063-4d97-93a0-f92b7326d348" />



Result:



The program successfully created a list of sample product reviews and applied TextBlob sentiment analysis to determine the emotional tone of each review
