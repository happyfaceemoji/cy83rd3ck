# cy83rd3ck

**A pocket-sized, open source music production instrument that runs in your browser.**

🎹 **[Try it live → happyfaceemoji.github.io/cy83rd3ck](https://happyfaceemoji.github.io/cy83rd3ck)**

*Open in Safari on iPhone for the full experience. No install, no account, free forever.*

-----

![cy83rd3ck screenshot](screenshot.png)

-----

## What is it?

cy83rd3ck is a complete music production instrument built with Web Audio API and React. It looks and feels like a hardware synth but runs entirely in your browser. It has a step sequencer, multiple synth engines, drum machines, an arpeggiator, a sample pad, a multitrack recorder, and a full-width piano keyboard — all in a single HTML file.

It was built by one person, a welder and self-taught developer from Vancouver, because this instrument didn’t exist and it should.

-----

## Features

### Sequencer

- 5 tracks: Kick, Snare, Hihat, Bass, Lead
- 16 or 32-step grid with per-step note and velocity editing
- 4 patterns with instant switching and chaining
- Swing, per-track step lengths, step probability
- Euclidean rhythms, Barlow indispensability, Markov chains, cellular automaton pattern generators

### Drum Machines (14)

TR-808 · TR-909 · LinnDrum · Oberheim DMX · Linn LM-1 · Roland CR-78 · Akai MPC60 · Alesis HR-16 · E-mu SP-12 · Simmons SDS-V · DMIX · and more

Each with independent tuning, decay, drive, pan, and velocity sensitivity per voice.

### Synth Engines (10)

Subtractive · 2-op FM · Wavetable · Karplus-Strong · Supersaw Pad · Additive Organ · FM Bell · 303 Acid · Juno Chorus · Granular

Full ADSR envelope, LFO with pitch/filter/amp targets, drive, chorus, bitcrush, shimmer.

### Performance

- Full-width 2-octave piano keyboard always visible
- Arpeggiator: Up, Down, Up/Down, Random, Chord modes
- Note repeat, tap tempo, metronome
- Pitch bend and mod sliders
- Per-track play modes: Normal, Retrigger, Gate, Slice, Pattern-LFO

### Recording & Arranger

- Deck recorder: records the live mix with real-time waveform display
- 8-track multitrack arranger with drag, cut, duplicate, undo
- WAV export and share
- Digest mode: auto-slices a recording into sample pads
- Sampler with 8 pads, auto-chop, waveform editor

### MIDI & Connectivity

- MIDI output to hardware devices
- BBS: post and load beats from other users in real time
- Sync Jam: sync BPM and patterns with other players
- Peer audio: stream your master output to another player over WebRTC
- Live online user counter

### Other

- 7 visual skins
- Mixer with per-track volume, pan, mute, solo, EQ
- Reverb, delay, sidechain compressor
- Auto-save to localStorage
- Leet speak mode, glitch easter egg

-----

## Hardware

The long-term goal is to turn cy83rd3ck into a real physical instrument. The hardware design is complete — schematics, enclosure drawings, and component spec all exist. A Crowd Supply campaign is in progress to fund the first prototype.

**Planned hardware spec:**

- Raspberry Pi CM4 running Chromium kiosk
- 5” 800×480 IPS touchscreen
- 2× OLED displays (info bar + waveform)
- 2-octave physical keyboard with FSR velocity sensing
- Teensy 4.1 USB MIDI controller
- Physical buttons, sliders, RGB LEDs
- USB DAC → 3.5mm audio output
- LiPo battery, USB-C charging
- iPhone-sized portrait form factor

-----

## Tech Stack

- **React** — UI
- **Web Audio API** — all sound synthesis and processing, no audio libraries
- **esbuild** — single-file HTML build targeting Safari 16
- **Supabase Realtime** — BBS, Sync Jam, online counter
- **WebRTC** — peer audio streaming
- **GitHub Pages** — hosting

No framework. No audio library. Every synth engine, drum machine, and effect is written from scratch in vanilla Web Audio API.

-----

## Build

```bash
# Clone
git clone https://github.com/happyfaceemoji/cy83rd3ck

# Install esbuild (via tsx)
npm install -g tsx

# Build
head -2 entry.tsx > /tmp/ce.tsx
tail -n +2 cyberdeck_v5.jsx >> /tmp/ce.tsx
echo "const _root = ReactDOM.createRoot(document.getElementById('root'));" >> /tmp/ce.tsx
echo "_root.render(React.createElement(Cyberdeck));" >> /tmp/ce.tsx

esbuild /tmp/ce.tsx \
  --bundle \
  --jsx=transform \
  --jsx-factory=React.createElement \
  --platform=browser \
  --target=safari16 \
  --minify \
  --outfile=index.html
```

Output is a single self-contained HTML file. Deploy anywhere.

-----

## License

MIT — do whatever you want with it. Build your own. Make it better. Ship a hardware version.

-----

## Links

- **Live app:** [happyfaceemoji.github.io/cy83rd3ck](https://happyfaceemoji.github.io/cy83rd3ck)
- **Hackaday.io:** [hackaday.io/happyfaceemoji](https://hackaday.io/happyfaceemoji)
- **Crowd Supply:** coming soon

-----

*Built by a welder from Vancouver who wanted this instrument to exist.*
