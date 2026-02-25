# 📝 Static Exam Website (MVP)

A lightweight, vanilla JavaScript examination platform. This project is built as an MVP to help students practice exams with features like timers, scoring, and history—all running locally in the browser.

---

## 📂 Project Structure
The project is organized to support a 5-person team working on different modules simultaneously. The project is deployed on: https://basicwebsiteproject.vercel.app/

```
/exam-site
├── index.html          # Home: Set subject, question count, and time
├── play.html           # Exam: Core test-taking interface
├── score.html          # Score: Results and performance summary
├── history.html        # History: List of all past attempts
├── review.html         # Review: Detailed check of correct/wrong answers
├── /data
│   └── questions.json  # Centralized question bank (JSON data)
├── /assets
│   └── style.css       # Global styling (Flexbox, buttons, cards)
└── /js
    ├── data.js         # Logic for fetching data from questions.json
    ├── engine.js       # Core logic (Shuffling, picking, scoring)
    ├── timer.js        # Countdown and auto-submit logic
    ├── storage.js      # LocalStorage API (save/load attempts)
    ├── ui.js           # UI helper functions for rendering components
    ├── main-index.js   # Main script for index.html
    ├── main-play.js    # Main script for play.html
    ├── main-score.js   # Main script for score.html
    ├── main-history.js # Main script for history.html
    └── main-review.js  # Main script for review.html
```

---

## 🏗️ Git Workflow for the Team
Follow these steps to avoid code conflicts.

### 1. Initial Setup
```bash
git clone <repository-url>
cd exam-site
```

### 2. Daily Routine
1. Pull the latest code:
   ```bash
   git pull origin main
   ```
2. Do your coding and testing.
3. Save and Push:
   ```bash
   git add .
   git commit -m "feat: your feature description"
   git push origin main
   ```

---

## 📊 Data Contracts

### 1. Question Format (Stored in /data/questions.json)
```json
{
  "id": "M01",
  "subject": "Math",
  "prompt": "12 * 12 = ?",
  "options": ["124", "144", "132", "148"],
  "correctIndex": 1,
  "difficulty": "easy"
}
```

### 2. Attempt Format (Stored in LocalStorage)
```json
{
  "attemptId": "2026-02-24T12:30:00.000Z",
  "subject": "Math",
  "total": 10,
  "correctCount": 8,
  "scorePct": 80,
  "timeUsedSec": 521,
  "questions": [...],
  "answers": [1, 0, null, 2]
}
```

---

## 🚀 How to Run
Since we use ES6 Modules (type="module"), you must use a local server:

1. VS Code Live Server: Right-click index.html -> "Open with Live Server".
2. Python: Run the following command and visit http://localhost:5500:
   ```bash
   python -m http.server 5500
   ```

---

## 👥 First week tasks: HTML/CSS Skeleton & Navigation
- **Person A (Integrator):** Initialize the GitHub repository and set up the exact folder structure. Create the base `index.html` and ensure all 5 pages are correctly linked via buttons to test navigation.
- **Person B (UI/UX Designer):** Create the global `assets/style.css` file. Define common styles: the main container width, typography, and a consistent button component that the whole team will use.
- **Person C (Exam Layout):** Build the HTML structure for `play.html`. Create the placeholders for the question card, the list of answer options (as clickable blocks), and the navigation footer (Next, Prev, Submit).
- **Person D (Home & Score Layout):** Build the HTML for `score.html` (the final result card with buttons to Restart, Review, or view History). Note: the Restart button navigate user to homepage.
- **Person E (History & Review Layout):** Build the HTML for `history.html` (a list-style layout for past attempts, each attempt show Test date, subject, and point) and `review.html` (a stacked layout to compare user answers with correct answers).