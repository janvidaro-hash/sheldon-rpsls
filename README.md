# 🖖 Sheldon's Mind Reader: RPSLS

An adaptive, AI-powered Rock, Paper, Scissors, Lizard, Spock game that learns your habits and actively uses probability to crush you. 

Originally built as a lightweight responsive web app, this project has evolved into a standalone **native Android application** featuring both single-player AI battles and a Pass-and-Play multiplayer mode.

[🎮 Play the Live Web Version Here](https://janvidaro-hash.github.io/sheldon-rpsls/)

---

## ✨ Features

* **Adaptive AI (Markov Chain Engine):** Sheldon doesn't guess randomly. The AI tracks your move history and calculates the statistical probability of your next move based on your previous choices.
* **Live Probability Telemetry:** Watch the AI's "brain" work in real-time. A dynamic UI panel shows exactly how confident the AI is in predicting your next move.
* **NEW: Human vs. Human Mode:** A local "Pass-and-Play" multiplayer mode. Player 1's choice is visually encrypted while passing the device to Player 2.
* **Cyberpunk UX:** A responsive, dark-mode neon interface with CSS animations, dynamic win/loss screen flashes, and physical "shake" effects for losing elements.
* **Bazinga!** Hidden audio triggers when the AI outsmarts you.
* **Android Native Wrapper:** Fully optimized to run as a native Android app via a locked-viewport WebView.

---

## 🧠 How the AI Works

This game ditches standard `Math.random()` logic (mostly). Instead, it uses an **n-gram pattern recognition model** (Markov Chain).

1.  **The Memory Matrix:** The game initializes a multidimensional object tracking every possible move transition.
2.  **Learning:** If you play *Rock*, the engine looks at its memory to see what you historically play *immediately after* Rock.
3.  **Countering:** If your history shows you play *Spock* 70% of the time after playing Rock, the AI anticipates Spock and automatically selects a counter-move (Lizard or Paper).
4.  **Randomness:** If you play completely randomly, the probability flattens out to 20% across the board, forcing the AI to revert to pure chance.

---

## 🛠️ Tech Stack

* **Frontend Game Logic:** Vanilla JavaScript (ES6)
* **Styling:** Pure CSS3 (Flexbox, CSS Variables, `@keyframes` animations)
* **Markup:** HTML5
* **Android Wrapper:** Kotlin, Android Studio (`WebView` implementation with local DOM storage enabled)
* **Hosting:** GitHub Pages

---

## 📱 How to Run the Android App

Want to run this as a native app on your Android device?

1. Clone this repository.
2. Open **Android Studio** and create a new **Empty Views Activity** project.
3. Navigate to the `app/src/main/` directory and create an `assets` folder.
4. Drop `index.html`, `bazinga.mp3`, and the 5 `.jpg` image files into the `assets` folder.
5. Replace the `activity_main.xml` layout with a single `WebView` component.
6. In `MainActivity.kt`, enable JavaScript, DOM Storage, and load the local asset URL:
   `webView.loadUrl("file:///android_asset/index.html")`
7. Click **Build > Build Bundle(s) / APK(s) > Build APK(s)** to generate your installable Android app!

---

## 📜 Rules of the Game
* **Scissors** cuts Paper & decapitates Lizard
* **Paper** covers Rock & disproves Spock
* **Rock** crushes Lizard & crushes Scissors
* **Lizard** poisons Spock & eats Paper
* **Spock** smashes Scissors & vaporizes Rock

---
*Built from scratch to compiled Android app in a single weekend. Bazinga.*
