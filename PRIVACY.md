# Privacy

Seventh Sense is designed privacy-first, by default and by architecture — not
as an afterthought.

## Core principles

- **Local-first inference.** Wherever technically possible, scoring and
  reasoning run on-device (primarily on the Snapdragon X Elite laptop's NPU).
  No signal has to leave the user's own devices for the system to function.
- **No raw content is ever collected or stored.** Seventh Sense does **not**
  collect, transmit, or store: raw audio, raw video, meeting content, chat
  content, coworker identities, or performance labels. This is explicitly out
  of scope, not merely unused.
- **Only derived, non-identifying signals are used.** Examples: "screen-active
  minutes," "ambient lux level," "stillness duration," "notification count in
  the last 10 minutes." These are aggregated/derived features, not raw
  sensor dumps.
- **User control.** The user decides which signal sources are enabled per
  device. Any device or signal type can be turned off without breaking the
  rest of the system (see [`docs/device-fallback-plan.md`](docs/device-fallback-plan.md)).
- **No medical claims.** Seventh Sense is a wellness and productivity signal
  tool. It does not diagnose, treat, or claim to detect any medical or mental
  health condition. It is not a substitute for professional medical advice.
- **No employee surveillance.** Seventh Sense is a personal, user-owned tool.
  It is not designed, marketed, or intended for employer-side monitoring of
  employees, and it does not report signals to any third party (employer,
  platform, or otherwise) by default.

## What is NOT collected

- Raw audio or raw video streams (RB3 Gen 2 Vision Kit runs feature
  extraction locally and does not store raw video by default)
- Meeting or call content, transcripts, or chat/message content
- Coworker or third-party identities (no face recognition)
- Performance ratings, labels, or evaluative judgments about the user or
  others

## Data retention

By default, all derived signals and scoring outputs are stored locally only.
See [`docs/data-collection-protocol.md`](docs/data-collection-protocol.md) and
[`docs/privacy-and-consent.md`](docs/privacy-and-consent.md) for the detailed,
per-device breakdown and the consent-flow skeleton.
