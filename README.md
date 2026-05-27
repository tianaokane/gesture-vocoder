# Gesture Vocoder

So this is a browser-based vocal synthesiser controlled entirely by hand gestures.

Speak or hum into your mic. Hold your hand up to your webcam. Move it to change pitch, reshape your fingers to change scale and timbre. No installation, no backend, just open and make noise.

[**Try it live →**](https://tianaokane.github.io/gesture-vocoder)

---

## How it works

Your voice is split into 16 frequency bands. Each band's loudness is measured in real time and used to puppet the same band in a synthesiser oscillator - so the synth breathes with your voice, carrying your rhythm and vowel shape but with a synthetic texture. This is called a vocoder.

Hand tracking runs in parallel via MediaPipe Hands, giving 21 landmark points per frame. Hand height maps to carrier pitch. Finger configuration maps to scale and timbre mode.

---

## Gestures (hope u appreciate my emojis)

| Gesture | Scale | Mode |
|---|---|---|
| ✋ Open hand | Major | Robot |
| 🤙 Thumb + pinky | Minor | Choir |
| ☝️ Index only | Pentatonic | Robot |
| ✌️ Index + middle | Chromatic | Choir |
| ✊ Fist | — | Silence |
| ↕️ Hand height | Pitch | — |

**Wear headphones.** The mic and speakers will feedback without them and you'll think I'm useless!

---

## Built with

- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - microphone input, oscillator bank, filter bank, convolution reverb
- [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) - real-time hand landmark detection
- Vanilla JavaScript, no frameworks, no build step

---

## Tips for playing it

- **Hum rather than speak** - sustained vowels give the vocoder the most to work with
- **Robot mode** sounds best with sharp, rhythmic humming
- **Choir mode** sounds best with slow, smooth hand movements and gentle singing
- **Fist to start** - begin in silence, then open your hand to activate
- The **pitch smoothing slider** controls how fast pitch glides between notes

---

## Run it locally

No build step needed. Clone the repo and open `index.html` in Chrome.

```bash
git clone https://github.com/yourusername/gesture-vocoder.git
cd gesture-vocoder
open index.html   # or just drag it into Chrome
```

Microphone and camera access require a browser permission prompt.
Local `file://` works fine for development. For sharing, use the hosted link above — mic and camera APIs require HTTPS, which GitHub Pages provides automatically.

---

*Built as part of a portfolio exploring browser-based audio and computer vision. I'm planning to expand this once I'm learning Unity for VR and might make it work on MetaQuest. We'll see!*
