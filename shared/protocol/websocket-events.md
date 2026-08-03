# WebSocket Events (Skeleton)

Event names/topics expected to flow over the local WebSocket hub hosted by
the Windows control surface. Payload details TBD — this is a topic-naming
skeleton only.

## Sensing topics (device → hub)

- `sensor.watch.feature_frame` — payload conforms to
  [`watch_feature_frame.schema.json`](../schemas/watch_feature_frame.schema.json)
- `sensor.rb3.context_frame` — payload conforms to
  [`rb3_context_frame.schema.json`](../schemas/rb3_context_frame.schema.json)
- `sensor.phone.context_frame` — payload conforms to
  [`phone_context_frame.schema.json`](../schemas/phone_context_frame.schema.json)
- `sensor.arduino.event_frame` — payload conforms to
  [`arduino_event_frame.schema.json`](../schemas/arduino_event_frame.schema.json)

## Control / state topics (hub ↔ device)

- `device.state` — payload conforms to
  [`device_state.schema.json`](../schemas/device_state.schema.json)
- `user.profile.update` — payload conforms to
  [`user_profile.schema.json`](../schemas/user_profile.schema.json)

## Dispatch topics (hub → device)

- `intervention.dispatch` — payload conforms to
  [`intervention.schema.json`](../schemas/intervention.schema.json)

## Open items

- TBD — exact envelope format (topic + payload vs. flat message).
- TBD — authentication/framing for the local WebSocket connection.
- TBD — verify against device SDK once each companion app is implemented.
