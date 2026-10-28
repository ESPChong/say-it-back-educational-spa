# Say It Back · Talking Times-Tables Practice

**Say It Back** is a voice-interactive Single Page Application (SPA) designed to help students practice times tables. Meet Abi, a friendly animated mascot who asks multiplication questions out loud. Students can answer by speaking or typing, leveraging retrieval practice and immediate corrective feedback to build long-term retention.

---

## Prerequisites

Because this app uses the browser's native Web Speech API for voice interaction, it is neccessary to use a Chromium-based browser (like **Google Chrome**, **Opera GX** or **Microsoft Edge**) for full functionality. 


***Important Note: Safari, Brave Browser and Mozilla Firefox are not compatible for this SPA***


You will also need either **Python** or **Node.js** installed on your machine to serve the files locally.

---

## How to Start

Since this is a static SPA, you simply need to serve the `index.html` file via a local web server. 

### Option 1: Using Python
If you have Python installed, navigate to the project's root directory in your terminal and run:

```bash
# Python 3
python -m http.server 8000

# Python 2 (if legacy)
python -m SimpleHTTPServer 8000
```

### Option 2: Using Node.js
If you have Node.js installed, you can use `npx` to run a temporary, zero-configuration local server:

```bash
npx http-server -p 8000
```

### Accessing the Application
Once your local server is running, open your web browser and navigate to:
👉 **[http://localhost:8000](http://localhost:8000)**

---

## Environment Variables

This project does **not** require any environment variables. It is a completely client-side application. All logic, speech recognition, and text-to-speech processing run directly in the user's browser. No API keys or backend configurations are needed.

---

## Voice Features (ASR & TTS)

This app utilizes the browser's native **Web Speech API**:
* **Text-to-Speech (TTS):** Abi the mascot speaks the math questions, hints, and feedback out loud using `window.speechSynthesis`.
* **Automatic Speech Recognition (ASR):** The app listens to the user's spoken answers using `window.SpeechRecognition` (or `webkitSpeechRecognition`).

*Note: If the browser does not support voice features or microphone permissions are blocked, the app gracefully falls back to typed input mode.*

---

## How to Complete One Interaction

1. **Select a Times Table:** 
   On the setup screen, click one of the number buttons (e.g., `7`) or choose the `Tricky mix · 6–9` to focus on the hardest facts. Click the **"Start practice"** button.
2. **Listen to the Question:** 
   Abi will introduce the round and ask the first question out loud (e.g., *"What is seven times eight?"*). The equation will appear on screen with a blank for the answer.
3. **Provide Your Answer:** 
   * **By Voice:** Wait for Abi to finish speaking, then say your answer out loud (e.g., *"Fifty-six"*). You will see your live transcription appear on the screen.
   * **By Typing:** Type the number (`56`) or the word (`fifty six`) into the input box and press **Enter** or click the **Answer** button.
4. **Receive Immediate Feedback:** 
   * If you get it right on the first try, Abi will confirm the correct answer and move to the next question. 
   * If you answer incorrectly or click **"I don't know"**, Abi will tell you the correct answer and ask you to *"say it back"* to reinforce learning. 
   **Note: This question will be added back into the queue to be asked again later in the round.**
5. **Review the Round Report:** 
   After completing 10 questions, you will see a Round Report showing which facts you got right on the first try, which you fixed after a retry, and which ones are still tricky. You can choose to practice the tricky ones again or pick a new table.

---

## Side Note - Challenge Details

This app was built to solve a challenge. The challenge details is as follows:

**Task - Edtech interaction app**
Build a small, playable interaction app for learning — not a slide deck and not a static website. A learner (or teacher) must be able to do something, get a response, and try again. Name one published learning idea (paper, textbook chapter, or curriculum source) and show how the interaction maps to it.

The app takes input, does something useful, and gives feedback in the same session. Input and output can be text, taps, voice, or a mix. One activity is enough.

Example (optional): you may use ASR (speech-to-text) and TTS (text-to-speech) so the learner talks and hears a reply — for instance a simple tutor face that listens, then speaks a short prompt. ASR/TTS is only an example. Typed or tap-based interaction is equally acceptable if the learning loop is clear.

Along with the 
