
import pandas as pd
import re
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.metrics import accuracy_score, classification_report


data = {
    'headline': [
        "The stock market saw a significant drop today due to inflation fears.",
        "The local team won the championship after a thrilling overtime finish.",
        "A new smartphone with advanced AI features was launched yesterday.",
        "The upcoming blockbuster movie broke all box office records on opening weekend.",
        "Interest rates have been increased by the central bank to stabilize the economy.",
        "The star athlete has signed a multi-million dollar contract with the new club.",
        "Tech giant releases a new operating system update fixing major security bugs.",
        "The pop singer's latest album debuted at number one on the charts."
    ],
    'category': [
        'Business', 'Sports', 'Technology', 'Entertainment',
        'Business', 'Sports', 'Technology', 'Entertainment'
    ]
}
df = pd.DataFrame(data)


def clean_text(text):
    text = text.lower()
    text = re.sub(r'\W', ' ', text) 
    text = re.sub(r'\s+', ' ', text) 
    return text.strip()


df['cleaned_headline'] = df['headline'].apply(clean_text)


X = df['cleaned_headline']
y = df['category']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)


vectorizer = TfidfVectorizer(stop_words='english', max_features=5000)
X_train_tfidf = vectorizer.fit_transform(X_train)
X_test_tfidf = vectorizer.transform(X_test)

model = MultinomialNB()
model.fit(X_train_tfidf, y_train)

y_pred = model.predict(X_test_tfidf)

print("--- Model Evaluation ---")
print(f"Accuracy: {accuracy_score(y_test, y_pred) * 100:.2f}%\n")
print("Classification Report:")
print(classification_report(y_test, y_pred, zero_division=0))


new_news = [
    "A revolutionary quantum computer has been built by scientists.",
    "Quarterback throws for 300 yards in major upset victory."
]

new_news_cleaned = [clean_text(news) for news in new_news]
new_news_tfidf = vectorizer.transform(new_news_cleaned)

predictions = model.predict(new_news_tfidf)

print("--- New Predictions ---")
for news, category in zip(new_news, predictions):
    print(f"Headline: '{news}'")
    print(f"Predicted Category: {category}\n")
