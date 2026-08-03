# Serial Commands (Skeleton) — Arduino UNO Q

Skeleton for the Arduino UNO Q serial command protocol. TBD/to be finalized
once firmware is written — do not treat these as final until verified
against the actual firmware implementation.

## Outbound (control surface → Arduino UNO Q)

- `PIXEL:SET:<r>,<g>,<b>` — set ambient pixel feedback color.
- `BUZZER:PULSE:<ms>` — trigger a gentle buzzer cue for `<ms>` milliseconds
  (optional module).

## Inbound (Arduino UNO Q → control surface)

- TBD — button press events (module: `buttons`)
- TBD — knob position events (module: `knob`)
- TBD — distance/presence readings (module: `distance`)
- TBD — thermo readings (module: `thermo`)

## Framing

- TBD — verify against device SDK for baud rate, line termination, and
  ack/nack behavior once firmware exists.

## Related

- [`../schemas/arduino_event_frame.schema.json`](../schemas/arduino_event_frame.schema.json)
- [`../../firmware/arduino-unoq/README.md`](../../firmware/arduino-unoq/README.md)
