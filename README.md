# Basic English Flashcards

A Progressive Web App (PWA) to practice Ogden’s 850 Basic English words using simple flashcards, spaced repetition, and daily study tracking. To test, use the link [https://datas2.github.io/basic-english/](https://datas2.github.io/basic-english/)

---

## Introduction

**Basic English** is a simplified vocabulary proposed by Charles Kay Ogden in the 1930s. The idea is that with just **850 carefully chosen words** it's possible to communicate in most everyday situations in English, serving as a solid foundation for beginners.

This application was created to help you learn and review these 850 words in a practical, easy, and continuous way. It works like a modern flashcard app, with support for **offline use**, **spaced repetition**, and visual study statistics, similar to a GitHub contribution graph.

---

## How to Use

### Accessing the app

You can use the app directly in your browser by accessing:

```text
https://datas2.github.io/basic-english/
```

It was designed to work well on both desktop and mobile (including iPhone).

## Install as an app (PWA)

- Desktop (Chrome/Edge):
    - Open the app's URL.
    - In the browser menu, choose Install / Install app (or similar).
    - The app will be installed as a stand-alone application on your system.

- iPhone (Safari):
    - Open the URL in Safari.
    - Tap Share (square icon with an upward-pointing arrow).
    - Select Add to Home Screen.
    - Confirm the name and tap Add.
    - After that, use the icon created on the home screen to open the app in app mode.

## Practicing with Flashcards

- When you open it, you will see a card with a word and the **“Show meaning”** button.
- Try to remember the meaning before revealing it:
    - When you are ready, click “Show meaning”.
    - The card flips and shows:
        - The word,
        - The meaning,
        - Two buttons: **“I knew it”** and **“I didn’t know”**.
    - Answer honestly:
        - **“I knew it”**: indicates that you knew the word.
        - **“I didn’t know”**: indicates that you didn’t remember or didn’t know it.
    - The app records your answer, updates your progress, and shows the next card.

## Resetting Progress

If you want to start from scratch: - Click “Reset progress”.

    - This erases the saved history and resets the statistics, but keeps the words.

# Features

## 🔠 Flashcards of 850 Basic English Words

- Loads all words from a local words.json file (each item with word and meaning).
- Shows one card at a time, with:
    - Front: only the word and the “Show meaning” button.
    - Back: word, meaning, and answer buttons.

## 🔁 Simple Spaced Repetition (SRS)

- Each word has a **strength level** and a record of **last seen**.
- When you click **“I knew it”**:
    - The word's strength increases, and the interval between reviews tends to get longer.
- When you click **“I didn’t know”**:
    - The strength decreases, and it is prioritized for earlier reviews.
- The next card is chosen based on a heuristic that considers:
    - Whether you have seen the word before,
    - The current strength,
    - How long ago it was reviewed.
- Result: New and difficult words appear more frequently; mastered words become less frequent.

## 💾 Persistent progress with localStorage

- Progress is saved in the browser using localStorage, including:
    - **seen**: words you have seen at least once,
    - **correct**: words you have marked as “I knew it”,
    - **incorrect**: words you have marked as “I didn’t know”,
    - **srs**: spaced repetition status (strength and last contact),
    - **daily**: statistics per day (correct/incorrect).
- You can close the app and come back later — the history will be kept locally until you use **Reset progress**.

# 📊 Detailed study statistics

Just below the flashcard you see two lines of statistics: - **Main line (overall progress)**: - **Mastered**: percentage of words considered mastered (you have gotten it right at least once and never marked it as wrong). - **Seen**: How many words you have seen in relation to the total of 850. - **Accuracy**: Overall accuracy rate (correct answers/total responses), with a ✓ / ✗ ​​count. - **SRS Line (Mastery Levels)**: - **Beginner**: How many words are at the beginner level (strength ≤ 0). - **Intermediate**: Intermediate level (strength between 1 and 3). - **Advanced**: Advanced level (strength ≥ 4). - **Hard**: Difficult words (strength ≤ −1), that is, words you frequently get wrong.

## 📅 Daily graph in the style of “GitHub contributions”

- A small square graph shows the activity of the last 30 days.
- Each square represents a day:
    - **Gray**: No studies recorded on that day.
    - **Blue**: you studied that day, with the intensity of the color based on the accuracy of the day:
        - **Darker** blue → low accuracy (more errors).
        - **Lighter** blue → high accuracy (more correct answers).
- When passing the mouse
    - If you hover over a small square (on desktop), you'll see a tooltip with:
        - Date,
        - Number of correct answers,
        - Number of errors,
        - Accuracy for that day.

# 📱 Offline-First PWA

Works like a Progressive Web App:

- **Offline support**:
    - The service-worker.js file pre-caches essential files (index.html, app.js, style.css, words.json, offline.html, etc.).
    - If you are offline and the resource is cached, the app continues to function normally.
    - If the resource is not cached, it displays an offline.html page with the message: **You are offline and this resource is not cached**.

- **Installable**:
    - Can be installed on desktop (Chrome/Edge) via the browser menu.
    - On iPhone, it can be added to the Home Screen via Safari.

# 🧩 No frameworks – pure JavaScript

- The app is built only with:
    - HTML + CSS (Bootstrap + custom styles)
    - Pure JavaScript (app.js).
    - There is no dependency on heavy frameworks (React, Vue, etc.), which facilitates code readability and customization.
