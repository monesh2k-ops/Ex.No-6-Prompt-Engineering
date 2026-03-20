#Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

##Aim: 

Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools.

##Explanation:

Develop a python code that integrates multiple AI tool by interacting with their APIs.
Compare outputs from different APIs.
Analyze the response and the Output.

The aim is to understand how to request help from AI tools for tasks like writing Python code, integrating with API##s, comparing outputs, and generating actionable insights.

##Code:
```
from nltk.sentiment import SentimentIntensityAnalyzer
import nltk

try:
    nltk.data.find('sentiment/vader_lexicon')
except LookupError:
    nltk.download('vader_lexicon', quiet=True)

# Simulated AI-generated text
generated_text = "This smartphone offers outstanding battery life and an intelligent AI camera that captures stunning photos."

print("Generated Review:\n")
print(generated_text)

# Sentiment analysis
sia = SentimentIntensityAnalyzer()
sentiment = sia.polarity_scores(generated_text)

print("\nSentiment Scores:")
print(sentiment)

# Improved Output Classification
print("\nFinal Review Result:")

if sentiment['compound'] >= 0.05:
    print("Positive Review ✅")
elif sentiment['compound'] <= -0.05:
    print("Negative Review ❌")
else:
    print("Neutral Review ⚖️")

# Insight
if sentiment['compound'] >= 0.05:
    print("Insight: The review is positive and suitable for marketing promotion.")
elif sentiment['compound'] <= -0.05:
    print("Insight: The review is negative and may affect product perception.")
else:
    print("Insight: The review is neutral.")
```
##output:
```
Generated Review:

This smartphone offers outstanding battery life and an intelligent AI camera that captures stunning photos.

Sentiment Scores:
{'neg': 0.0, 'neu': 0.556, 'pos': 0.444, 'compound': 0.8625}

Final Review Result:
Positive Review ✅
Insight: The review is positive and suitable for marketing promotion.
```

```
Generated Review:

This smartphone has disappointing battery life, and the so-called AI camera performs poorly, producing dull and unimpressive photos.

Sentiment Scores:
{'neg': 0.356, 'neu': 0.644, 'pos': 0.0, 'compound': -0.8074}

Final Review Result:
Negative Review ❌
Insight: The review is negative and may affect product perception.
```

```
Generated Review:

This smartphone offers moderate battery life, and its AI camera captures photos with decent quality.

Sentiment Scores:
{'neg': 0.0, 'neu': 1.0, 'pos': 0.0, 'compound': 0.0}

Final Review Result:
Neutral Review ⚖️
Insight: The review is neutral.
```
##Result: 
The Python program was successfully developed to simulate integration with multiple AI tools and perform sentiment analysis on generated text using the VADER sentiment analyzer from NLTK.
