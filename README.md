# AI Voice Assistant

A wake-word voice assistant that checks your Google Calendar and takes notes, entirely by voice.

## How it works

- Listens continuously via microphone (`speech_recognition` + Google's speech API) for the wake word **"hey aous"**.
- Once woken, understands two kinds of commands:
  - **Calendar queries** ("what do I have today", "am I busy tomorrow") — parses the spoken date, calls the Google Calendar API (OAuth2), and reads events back with text-to-speech (`pyttsx3`).
  - **Notes** ("make a note", "remember this") — takes the next spoken phrase and saves it as a timestamped `.txt` file, opened automatically in Notepad.

## Stack

Python, Google Calendar API (`google-api-python-client`, OAuth2), `SpeechRecognition`, `pyttsx3`.

## Setup

1. Create a Google Cloud project, enable the Calendar API, and download OAuth credentials as `credentials.json` in the project root.
2. Install dependencies: `google-api-python-client`, `google-auth-oauthlib`, `google-auth-httplib2`, `SpeechRecognition`, `pyttsx3`, `pytz`, `pyaudio`.
3. Run the notebook. On first run it opens a browser window for Google OAuth consent and caches the token in `token.pickle`.

`credentials.json` and `token.pickle` are per-user secrets and are not included in this repo — generate your own via the Google Cloud Console.
