---
layout: post
title: "Text to Audio Transcription with Speaker Diarization"
author: Zhien Li
category: projects
tags:
  - content: Web Dev
  - content: AI/ML
preview: projectImg/tts_tool1.jpg
align: align-left
urlLinks:
  - url: https://github.com/li6834300/whisper_trans
    name: GitHub Repository
---

I developed a web application that automatically **transcribes audio files and identifies different speakers** in conversations using OpenAI's Whisper model and speaker diarization technologies, creating a powerful tool for transcription needs.

## {{page.title}}
-----

This project combines modern web technologies with state-of-the-art AI models to create an easy-to-use tool for transcribing speech with speaker identification. Key features include:

- **Modern User Interface:**
    * Clean, intuitive web interface with drag-and-drop file uploads
    * Real-time progress tracking during transcription processing
    * Responsive design that works on various devices
    * Support for 18 languages in the user interface

- **Powerful Transcription Engine:**
    * Integration with OpenAI's Whisper speech recognition models
    * Multiple model sizes (tiny, base, small, medium, large) to balance speed and accuracy
    * Speaker diarization to identify and separate different speakers in the conversation
    * Support for various audio formats (MP3, WAV, OGG, FLAC, M4A)

- **Flexible Output Options:**
    * Download transcriptions in multiple formats (TXT, JSON, SRT, VTT)
    * Timestamped transcripts with speaker identification
    * Clean formatting for easy reading and post-processing

This tool significantly improves productivity for anyone working with audio transcription - from journalists and researchers to content creators and accessibility professionals.

The application is built using Flask for the backend, with a modern JavaScript frontend. It incorporates several advanced technologies including PyTorch, OpenAI Whisper, and Pyannote Audio for speaker diarization.

---

![Audio Transcription Tool Interface]({{ site.url }}/images/projectImg/tts_tool1.jpg){:class="content-img-middle"}
![Transcription Results Example]({{ site.url }}/images/projectImg/tts_tool2.jpg){:class="content-img-middle"} 