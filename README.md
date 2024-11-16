# Audio QA Pipeline

This repository contains an end-to-end pipeline for processing audio data, transcribing it, refining the transcriptions, and answering questions based on the refined text. The pipeline uses state-of-the-art models for automatic speech recognition (ASR), transcription refinement, and question-answering (QA).

---

## Overview

The pipeline consists of the following stages:
1. **Transcription with ASR Model**: Converts audio into text.
2. **Transcription Refinement**: Improves the quality of transcriptions.
3. **Question Answering**: Answers questions posed in audio form by leveraging refined text transcriptions.

---

## Workflow

1. **Audio Transcription**:
   - The audio files are processed using the `ASR_Model` notebook to produce raw transcriptions.

2. **Refinement**:
   - The `Refinement` notebook takes the raw transcriptions and applies refinement techniques to improve their accuracy and coherence.

3. **Final QA**:
   - The `Final_QA` notebook uses the refined transcriptions to answer questions. The workflow involves:
     - Transcribing the question (in audio form) using OpenAI's Whisper model.
     - Answering the question based on the refined transcription.

---

## Required Libraries

The following libraries are required to run the notebooks. Install them using the provided `requirements.txt`.

### Key Dependencies
- **Speech Recognition**:  
  - `whisper` (for audio transcription)
  - `torchaudio` (audio processing)
- **NLP and Refinement**:
  - `transformers` (Hugging Face models)
  - `nltk` (text preprocessing and refinement)
  - `sentencepiece` (tokenization)
- **QA System**:
  - `openai` (for GPT-based work)
  - `Gemini API and Hugging Face models` (optional, for advanced QA workflows)
- **Others**:
  - `numpy`
  - `pandas`
  - `torch`
  - `gradio` (for frontend for QA system)

### Install Dependencies
No need every notebook first installs required liberaries
## Usage

### Step 1: Transcription
1. Place your audio files in the `audio_input/` directory.
2. Open and run the `ASR_Model.ipynb` notebook.
3. Raw transcriptions will be saved to the `all_transcription.txt` folder.

### Step 2: Refinement
1. Open and run the `Refinement.ipynb` notebook.
2. The notebook will read the raw transcriptions from `all_transcription.txt`.
3. Refined transcriptions will be saved to the `final_combined_output.txt` file.

### Step 3: Question Answering
1. Open and run the `Final_QA.ipynb` notebook.
2. You will get gradio user interface, you can upload audio question or use microphone option to record question and submit
3. The notebook will transcribe the questions and answer them using the refined text.
4. Answers will be shown after processing the input question via QA system and it will appear on userinterface.
