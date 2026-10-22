# Changelog

## 0.0.7-alpha

- Migrated Voice call tools to Voice API v2 with project OAuth credentials and optional Voice Service selection. Added call listing, session lookup, Voice Service creation, number assignment, webhook configuration, TTS call batches, and batch status retrieval.
- **Breaking:** Removed `conference-callout`, `manage-conference-participant` and `close-conference`. They relied on Voice API v1 application credentials, and will return on Voice API v2 with project credentials once conferences are available there (planned Q1 2027).
- **Breaking for `tts-callout`:** `phoneNumber` must now be a valid E.164 number (for example, `+14155550123`). Values in local or non-E.164 formats that were previously accepted by the tool schema are now rejected before the API request is made.
- **Breaking for stdio:** the server no longer exports OpenTelemetry traces or metrics, even with `OTEL_EXPORTER_OTLP_ENDPOINT` set. Tool spans and metrics go to the no-op `@opentelemetry/api` providers.
