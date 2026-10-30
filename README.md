# Guitar Tools · 吉他练习工具箱

A browser-based guitar practice prototype built with Next.js, TypeScript, Tailwind CSS and the Web Audio API.

把调音、节拍、指板和基础乐理练习集中在一个浏览器界面中。

## Archived personal experiment / 已归档的个人实验

Originally a toy project for exploring browser-based guitar tools. This repository is retained as a learning record and is no longer actively maintained. It is an experimental prototype; audio accuracy and reliability have not been systematically validated.

最初是一个玩具项目，现保留代码作为学习与探索记录，不再主动维护。音频准确性与稳定性尚未经过系统验证，不应视为专业级练习工具。

## Explore the tools

| Route | Tool |
| --- | --- |
| `/tuner` | Microphone-based tuner and reference tones |
| `/metronome` | Tempo and beat controls |
| `/chords` | Chord diagrams |
| `/scales` | Scale patterns |
| `/fretboard` | Interactive fretboard |
| `/circle-of-fifths` | Key relationships |
| `/progressions` | Chord progression reference |
| `/theory` | Music theory reference |
| `/ear-training` | Interval and chord exercises |
| `/practice-sessions` | Practice timer and sessions stored in this browser |

This is a practice prototype. Tuner accuracy, audio timing, accessibility and cross-browser behavior still need systematic validation. Browser storage is local to the device and is not an account or cloud backup.

## Run locally

Use Node.js compatible with the pinned Next.js 13.5.1 dependency and npm.

```bash
git clone https://github.com/zhangfeng0423/guitar-tools.git
cd guitar-tools
npm ci
npm run dev
```

Open http://localhost:3000 . Allow microphone access when trying the tuner. Browsers require a secure context for microphone use: localhost during development, or HTTPS when hosted. Audio playback may require a user gesture.

## Build a static site

```bash
npm run lint
npm run build
```

`next.config.js` uses `output: 'export'`; the build writes a static site to `out/`. Serve that folder with a static HTTP server or static hosting. The `start` script invokes `next start`, which does not serve this export configuration.

The build configuration skips ESLint during builds, so run `npm run lint` separately. A successful build alone is not lint verification.

## Source guide

- [app](app): pages for each tool
- [hooks/use-microphone.ts](hooks/use-microphone.ts): microphone access
- [lib/audio-utils.ts](lib/audio-utils.ts) and [lib/audio-player.ts](lib/audio-player.ts): audio helpers
- [lib/music-theory.ts](lib/music-theory.ts): music theory data and helpers
- [components](components): shared interface components

## Status

No hosted demo is currently listed in this repository. The code remains available for reference and local exploration. GitHub archiving makes the repository read-only; active support and issue handling are not provided.

There is currently no LICENSE file in this repository. The previous MIT statement was not backed by a license file.
