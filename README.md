# 🎙️ The Empathy Engine -- Giving AI a Human Voice

## 📌 Project Description

The Empathy Engine is an AI-powered speech synthesis system that
dynamically modifies vocal characteristics based on the detected emotion
of input text.

Traditional Text-to-Speech (TTS) systems produce flat and robotic
output. This project enhances voice interaction by:

-   Detecting emotional tone using sentiment analysis
-   Mapping emotion to expressive voice parameters
-   Generating emotionally adaptive speech output

The system supports granular emotion detection, intensity-based
modulation, and a web-based interface built using FastAPI.

------------------------------------------------------------------------

## 🎯 Objective

The objective of this project is to:

1.  Accept text input from the user\
2.  Detect the emotional tone of the text\
3.  Map detected emotion to specific vocal parameters\
4.  Generate a playable audio file with expressive speech

This demonstrates the integration of Natural Language Processing (NLP)
with speech synthesis to create more human-like AI communication.

------------------------------------------------------------------------

## 🛠️ Technology Stack

-   Python 3.10\
-   FastAPI (Web Framework)\
-   VADER Sentiment Analysis (Emotion Detection)\
-   pyttsx3 (Offline Text-to-Speech -- Windows SAPI5)\
-   Jinja2 (HTML Templates)

------------------------------------------------------------------------

## 📂 Project Structure

```
empathy_engine/
│
├── app/
│   ├── main.py
│   ├── emotion_detector.py
│   ├── tts_engine.py
│   ├── static/
│   │   └── (generated audio files)
│   └── templates/
│       └── index.html
│
└── README.md
```

------------------------------------------------------------------------

## ⚙️ Setup Instructions (Windows + Conda)

### Step 1: Clone the Repository

git clone `<your-repo-url>`{=html} cd empathy_engine/app

### Step 2: Create Conda Environment

conda create -n empathy_engine_env python=3.10 conda activate
empathy_engine_env

### Step 3: Install Dependencies

pip install fastapi uvicorn pyttsx3 vaderSentiment jinja2
python-multipart

### Step 4: Run the Application

uvicorn main:app

Open your browser and go to:

http://127.0.0.1:8000

------------------------------------------------------------------------

## 🧪 How to Test

Try entering different emotional sentences:

Excited: Wow! This is absolutely incredible and amazing!

Angry: This is the worst experience ever.

Concerned: I am a bit worried about the results.

The system will:

-   Detect emotion\
-   Display intensity score\
-   Generate expressive audio\
-   Automatically play the audio

------------------------------------------------------------------------

## 🧠 Emotion Detection Logic

The system uses VADER Sentiment Analyzer to compute a compound sentiment
score between -1 and +1.

### Emotion Classification Rules

-   ≥ 0.6 → Excited\
-   0.3 -- 0.59 → Happy\
-   -0.29 -- 0.29 → Neutral\
-   -0.3 -- -0.59 → Concerned\
-   ≤ -0.6 → Angry

------------------------------------------------------------------------

## 🎙️ Emotion-to-Voice Mapping Logic

Base Voice Settings:

-   Base Rate: 170\
-   Base Volume: 0.9

Voice Modulation Strategy:

-   **Excited** → High rate increase, maximum volume\
-   **Happy** → Moderate rate increase, high volume\
-   **Angry** → Slight rate increase, strong emphasis\
-   **Concerned** → Reduced rate, lower volume\
-   **Neutral** → Default rate and volume

------------------------------------------------------------------------

## 🔥 Intensity Scaling

Voice modulation is proportional to emotional intensity.\
Stronger emotional scores result in greater speech parameter
adjustments.

------------------------------------------------------------------------

## 🏗️ Design Decisions

1.  Offline TTS (pyttsx3) to avoid API costs\
2.  Unique audio file generation using UUID to prevent caching
    conflicts\
3.  New TTS engine per request to prevent blocking issues\
4.  Cache-busting strategy to avoid browser caching problems\
5.  Granular emotion categories for richer modulation

------------------------------------------------------------------------

## 🚀 Features Implemented

✔ Text input interface\
✔ Granular emotion detection (5 categories)\
✔ Intensity-based voice scaling\
✔ Dynamic speech modulation\
✔ FastAPI web interface\
✔ Offline execution\
✔ Auto audio playback

------------------------------------------------------------------------

## 🏆 Conclusion

The Empathy Engine demonstrates how sentiment analysis and speech
synthesis can be combined to build emotionally adaptive AI systems.

This project highlights applied NLP, backend architecture, and
human-centered AI voice interaction.

------------------------------------------------------------------------

## 👨‍💻 Author

Vishal Singh\
AI Systems Developer
