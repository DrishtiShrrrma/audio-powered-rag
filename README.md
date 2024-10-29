<img width="554" alt="image" src="https://github.com/user-attachments/assets/e4bf4735-803c-464d-af56-aee964484d73">

to do: suggest refined questions


Start: Multilingual Pipeline
|
|--> **Audio Input & Processing**
|    |
|    |--> Record Audio (5 seconds)
|    |--> Save as .wav file
|    |--> Transcribe Audio (Whisper Large V3 Turbo)
|    |--> Output: Transcription Text
|
|--> **Language Detection & Translation**
|    |
|    |--> Detect Transcription Language
|    |--> Check if transcription language matches document language
|         |
|         |-- Yes --> Continue with aligned transcription
|         |
|         |-- No --> Translate transcription to match document language
|    |--> Output: Aligned Transcription
|
|--> **Document Processing & Splitting**
|    |
|    |--> Load Document (PDF/Other Formats)
|    |--> Split Document into Chunks
|    |--> Detect Document Language
|    |--> Output: Document Chunks
|
|--> **Vector Store & Retrieval**
|    |
|    |--> Embed Document Chunks with HuggingFace Model
|    |--> Store Chunks in Vector Database (Chroma)
|    |--> Setup RetrievalQA (Adaptive Settings)
|    |--> Input: Transcription/Question
|    |--> Retrieve Relevant Documents
|    |--> Output: Answer & Confidence Scores
|
|--> **Answer Processing & Analysis**
|    |
|    |--> Perform Sentiment Analysis
|    |--> Check if Answer is longer than 100 words
|         |
|         |-- Yes --> Summarize Answer (Gemma2-9B-IT Model)
|         |
|         |-- No --> Use Original Answer
|    |--> Output: Processed Answer
|
|--> **Output Alignment & Text-to-Speech**
|    |
|    |--> Check if final answer language matches original transcription language
|         |
|         |-- Yes --> Continue with final answer
|         |
|         |-- No --> Translate Answer to Original Language
|    |--> Convert Answer to Speech (XTTS-v2)
|    |--> Save as 'response_audio.wav'
|
|--> End: Multilingual Pipeline Completed

