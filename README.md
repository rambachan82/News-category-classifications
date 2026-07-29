# The Classifier Gazette 📰

A single-page web application that reads a news article, headline, or short blurb and automatically assigns it to one of eight newspaper sections: **Politics, Business, Technology, Sports, Health, Entertainment, Science,** or **World**.

Designed as a vintage newsroom-style **assignment desk**, the application features a colorful newspaper-inspired interface, live word counting, confidence scoring, and a ranked breakdown of every category.

---

# Features

* **Instant Classification** – Paste any news article or headline and receive a predicted newspaper section in under a second.
* **Confidence Breakdown** – Displays a ranked percentage score for all eight categories using an interactive bar chart.
* **Sample Articles** – Try the classifier instantly using built-in Politics, Sports, Technology, and Health examples.
* **Live Word Count** – Tracks the number of words as you type.
* **Keyboard Shortcut** – Press **Ctrl/Cmd + Enter** to classify instantly.
* **Responsive Design** – Optimized for desktop, tablet, and mobile devices.
* **Zero Dependencies** – Everything is contained in a single HTML file with no build tools or server required.

---

# Categories

| Section       | Example Keywords                                |
| ------------- | ----------------------------------------------- |
| Politics      | election, senate, president, legislation, vote  |
| Business      | market, stock, revenue, merger, IPO             |
| Technology    | software, AI, chip, cloud, algorithm            |
| Sports        | match, championship, goal, athlete, medal       |
| Health        | vaccine, hospital, patient, outbreak, treatment |
| Entertainment | film, album, celebrity, box office, premiere    |
| Science       | research, discovery, NASA, telescope, quantum   |
| World         | border, conflict, treaty, refugee, ceasefire    |

---

# How It Works

The application uses a **keyword-weighted heuristic classifier** instead of a machine learning model.

### Classification Process

1. The user enters or pastes a news article or headline.
2. The text is converted into a standardized format.
3. Every word is compared with the keyword lexicon of each newspaper section.
4. Matching keywords are counted for every category.
5. Match counts are converted into confidence percentages.
6. The highest-scoring category is selected as the predicted newspaper section.
7. The confidence chart and ranked category breakdown are displayed.

This approach makes the application lightweight, fast, and capable of running entirely inside the browser without external libraries.

---

# Getting Started

No installation is required.

1. Download **`newspaper-classifier.html`**.
2. Open the file using any modern web browser (Chrome, Firefox, Safari, or Edge).
3. Paste a news article or click one of the sample headlines.
4. Click **Send to the Desk** (or press **Ctrl/Cmd + Enter**) to classify the article.

For deployment, upload the HTML file to any static hosting platform such as GitHub Pages, Netlify, Vercel, or Amazon S3.

---

# Project Structure

```text
newspaper-classifier.html
│
├── HTML Structure
├── CSS Styling
├── JavaScript Logic
│   ├── Category Keywords
│   ├── Sample Articles
│   ├── Classification Algorithm
│   └── Result Visualization
```

---

# Customization

The project is designed to be easy to modify.

* **Add New Categories** – Update the `CATEGORIES` object inside the `<script>` section.
* **Edit Keywords** – Modify the `words` array for each category.
* **Add Sample Articles** – Update the `SAMPLES` array.
* **Change the Theme** – Modify the CSS custom properties (`--paper`, `--ink`, `--stamp-red`, etc.) at the top of the stylesheet.

---

# Limitations

This application is intended as a **heuristic prototype** rather than a production-ready text classifier.

Current limitations include:

* Relies only on keyword matching.
* Cannot understand context or semantics.
* May misclassify articles containing overlapping vocabulary.
* Does not support multi-label classification.

---

# Future Enhancements

Possible improvements include:

* Train a machine learning model (Naive Bayes, SVM, or Transformer).
* Use datasets such as **AG News** or **BBC News** for training.
* Serve predictions through a backend API.
* Support multi-label article classification.
* Automatically generate keywords using TF-IDF or other statistical methods.
* Improve confidence estimation using NLP techniques.

---

# License

This project is provided **as-is** for educational, demonstration, and prototyping purposes. You are free to modify and adapt it for your own projects.
