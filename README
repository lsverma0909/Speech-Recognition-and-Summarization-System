# 🎙️ Speech Recognition and Text Summarization System

This project automatically converts spoken audio into text and generates concise summaries using state-of-the-art Natural Language Processing (NLP) models. The system combines speech recognition, punctuation restoration, and transformer-based summarization to transform long audio recordings into readable summaries.

---

## 📌 Project Overview

Processing long audio recordings manually can be time-consuming. This project automates the workflow by:

1. Converting speech to text using Vosk.
2. Restoring punctuation and capitalization.
3. Generating concise summaries using Transformer-based NLP models.

The system can be used for:

- Meeting transcription
- Podcast summarization
- Lecture notes generation
- Interview transcription
- Voice memo summarization

---

## 🔄 Project Pipeline

```text
Audio File (.mp3)
        │
        ▼
 Speech Recognition
      (Vosk)
        │
        ▼
 Raw Transcript
        │
        ▼
 Punctuation Restoration
   (RecasePunc Model)
        │
        ▼
 Clean Transcript
        │
        ▼
 Text Summarization
 (Hugging Face Transformers)
        │
        ▼
 Final Summary
```

---

## 🛠 Technologies Used

- Python
- Vosk Speech Recognition
- PyDub
- Transformers (Hugging Face)
- PyTorch
- RecasePunc
- Regular Expressions (Regex)

---

## 📦 Dependencies

Install the required packages:

```bash
pip install vosk
pip install pydub
pip install regex
pip install torch
pip install transformers
```

---

## 🎤 Speech Recognition

The project uses the Vosk offline speech recognition engine to transcribe audio files into text.

### Features

- Offline speech recognition
- Fast transcription
- Supports long audio files
- Word-level recognition

Example:

```python
from vosk import Model, KaldiRecognizer

model = Model(model_name="vosk-model-en-us-0.22")
rec = KaldiRecognizer(model, 16000)
```

---

## 🎵 Audio Processing

Audio files are processed using PyDub.

### Preprocessing Steps

- Convert audio to mono channel
- Resample to 16 kHz
- Prepare audio for Vosk processing

Example:

```python
from pydub import AudioSegment

audio = AudioSegment.from_mp3("audio.mp3")
audio = audio.set_channels(1)
audio = audio.set_frame_rate(16000)
```

---

## 📝 Punctuation Restoration

Speech recognition models typically generate text without punctuation or capitalization.

The project uses the RecasePunc model to restore:

- Periods
- Commas
- Question marks
- Capital letters

Example:

```python
cased = subprocess.check_output(
    "python3 recasepunc.py predict checkpoint",
    shell=True,
    text=True,
    input=text
)
```

---

## 🎙️ Long Audio Support

To handle lengthy recordings efficiently, audio files are split into smaller segments before transcription.

### Benefits

- Improved recognition accuracy
- Reduced memory usage
- Better performance on long recordings

Example:

```python
step = 45000

for i in range(0, len(audio), step):
    segment = audio[i:i+step]
    rec.AcceptWaveform(segment.raw_data)
```

---

## 🤖 Text Summarization

After transcription, the text is summarized using Hugging Face Transformer models.

### Features

- Automatic summarization
- Handles long transcripts
- Produces concise, readable summaries

Example:

```python
from transformers import pipeline

summarizer = pipeline("summarization")
```

---

## 📄 Transcript Chunking

Transformer models have token limitations.

To process long transcripts:

- Split transcript into chunks
- Summarize each chunk
- Combine summaries into a final summary

Example:

```python
split_tokens = transcript.split(" ")

docs = []

for i in range(0, len(split_tokens), 850):
    docs.append(" ".join(split_tokens[i:i+850]))
```

---

## 🚀 How to Run

### Clone Repository

```bash
git clone https://github.com/your-username/Speech-Recognition-and-Summarization-System.git
cd Speech-Recognition-and-Summarization-System
```

### Install Dependencies

```bash
pip install vosk pydub regex torch transformers
```

### Add Audio File

Place your MP3 file inside the project directory:

```text
project/
│
├── audio.mp3
├── RecognizerandSummarizer.ipynb
└── ...
```

### Run Notebook

```bash
jupyter notebook RecognizerandSummarizer.ipynb
```

---

## 📁 Project Structure

```text
Speech-Recognition-and-Summarization-System/
│
├── RecognizerandSummarizer.ipynb
├── recasepunc/
│   ├── checkpoint/
│   └── recasepunc.py
│
├── transcript.txt
├── audio.mp3
├── README.md
└── requirements.txt
```

---

## 📊 Key Features

✅ Offline Speech Recognition

✅ Audio Preprocessing

✅ Automatic Punctuation Restoration

✅ Long Audio Transcription Support

✅ Transformer-Based Summarization

✅ End-to-End Audio-to-Summary Pipeline

---

## 🎯 Future Improvements

- Real-time speech recognition
- Support for multiple languages
- Speaker diarization
- Automatic keyword extraction
- Web application deployment
- Integration with meeting platforms

---

## 📚 References

- Vosk Speech Recognition
- Hugging Face Transformers
- PyTorch Documentation
- PyDub Documentation
- RecasePunc Project

---

## 👩‍💻 Author

**Lisa Verma**

Machine Learning | Natural Language Processing | Speech Processing

---

### ⭐ If you found this project useful, please consider giving it a star!
