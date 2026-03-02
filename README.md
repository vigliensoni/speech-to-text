# speech → text

A minimal, privacy-first speech-to-text app that runs entirely in the browser. No server, no account, no data ever leaves your device.

## Features

- **Real-time transcription** — interim results appear as you speak, finalized on sentence completion
- **Editable transcript** — click anywhere in the transcript to fix misheard words inline
- **Auto-save** — transcript is saved to `localStorage` and restored automatically on the next visit
- **Download as .txt** — export your transcript with a date-stamped filename
- **20 languages** — English (US/UK), Spanish, French, German, Italian, Portuguese, Russian, Hindi, Japanese, Chinese (Simplified/Traditional), Korean, Arabic, Dutch, Polish, Swedish, Turkish, Vietnamese
- **Reading time estimate** — shown once the transcript exceeds 50 words
- **Safe clear** — two-step confirmation, with a 4-second Undo window
- **Persistent language choice** — your last-used language is remembered across sessions
- **Zero dependencies** — single HTML file, no build step, no npm

## Usage

Open `speech-to-text.html` in Chrome, Edge, or Safari. That's it.

> The Web Speech API requires a Chromium-based browser (Chrome, Edge, Brave) or Safari. Firefox does not support it.

When prompted, allow microphone access. Click **Record** (or press `space`) to begin. The transcript updates in real time.

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Toggle recording on/off |
| `Ctrl`/`Cmd` + `D` | Download transcript as `.txt` |

`Space` works from anywhere on the page — except when you're typing inside the transcript editor.

## Controls

| Control | Description |
|---------|-------------|
| **Record / Stop** | Start or stop the microphone |
| **Language** | Select the speech language (saved for next visit) |
| **Download** | Save the transcript as `transcript-YYYY-MM-DD.txt` |
| **Copy** | Copy the transcript to the clipboard |
| **Clear** | Erase the transcript (requires confirmation, then 4s undo window) |

## Privacy

All processing is done by the browser's built-in speech recognition engine. On Chrome and Edge this sends audio to Google/Microsoft servers per the Web Speech API spec — the same engine used by those browsers' built-in voice features. No transcript data is sent anywhere else.

Safari uses on-device recognition and works fully offline.

## Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome 33+ | Full support |
| Edge 79+ | Full support |
| Safari 14.1+ | On-device, fully offline |
| Firefox | Not supported |
| Mobile Chrome (Android) | Supported |
| Mobile Safari (iOS 14.5+) | Supported |

## Running Locally

No build process — just open the file:

```bash
open speech-to-text.html        # macOS
start speech-to-text.html       # Windows
xdg-open speech-to-text.html    # Linux
```

Or serve it with any static server if you need `https://` for microphone access on non-localhost origins:

```bash
npx serve .
python3 -m http.server 8080
```
