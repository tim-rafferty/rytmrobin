# RytmRobin

![Untitled](https://github.com/user-attachments/assets/d8bf7479-3ea8-4c88-bbc3-080add12f7eb)

A web-based drum machine and sampler inspired by PureData and Strudel, React, and Web Audio.

## Features

- 4-track sampler with polyrhythmic capabilities
- Round-robin sample playback (up to 4 samples per track)
- Adjustable BPM and division
- Visual beat display
- Individual track controls for pattern, volume, and mute

## Getting Started

- Node.js (v14 or higher)
- npm or yarn

### Installation

1. Clone the repository: git clone https://github.com/tim-rafferty/rytmrobin.git

2. Install dependencies: npm install

3. Place your audio samples in the public/samples directory, the application comes with some default samples.

4. Start the development server: npm start

5. Open your browser to http://localhost:3000

### Basic Controls

- **Play/Pause**: Start or stop the sampler
- **BPM**: Adjust the tempo of the playback
- **Division**: Change the beat division (1/4, 1/8, 1/16, 1/32)
- **Reset**: Reset the pattern counter to the beginning

### Track Controls

- **Pattern Input**: Enter a pattern for each track (e.g., "0 1 2 3" for quarter notes)
- **Volume Slider**: Adjust volume for each track
- **Mute Button**: Mute/unmute individual tracks
- **Add Sample**: Add samples to a track (up to 4 per track)

### Pattern Syntax

The pattern input uses Strudel's pattern syntax:
- 0 1 2 3: Quarter notes (equally spaced)
- 0 0.5 1 1.5 2 2.5 3 3.5: Eighth notes
- 0.5 1.5 2.5 3.5: Off-beat eighth notes
- 0 2: Half notes
- 0 1 0 1: Basic kick-snare pattern

### Creating Complex Polyrhythms

To create interesting polyrhythms, set different patterns for each track with varying rhythmic values:

1. Track 1: 0 1 2 3 (4/4 rhythm)
2. Track 2: 0 1.5 3 (3/4 rhythm) 
3. Track 3: 0 1.2 2.4 3.6 (5/4 rhythm)

This will create a pattern that cycles every 60 beats (LCM of 4, 3, and 5).

### Round-Robin Sample Usage

Each track can have up to 4 samples loaded. When triggered, it will advance through the samples in a round-robin fashion, creating dynamic and evolving patterns.

## Technologies Used

- **Strudel.cycles**: For audio pattern generation and sample playback
- **React**: For the user interface
- **Web Audio API**: For audio processing
- **Tone.js**: For advanced audio capabilities

## Acknowledgments

- Inspired by PureData patches
- Built with [Strudel](https://strudel.tidalcycles.org/)
- Sample management with [Tone.js](https://tonejs.github.io/) 
