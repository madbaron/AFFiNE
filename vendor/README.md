# Vendored crates

## llm_adapter

`llm_adapter` 0.2.20 from crates.io (https://github.com/darkskygit/llm_adapter,
AGPL-3.0-only), wired in through `[patch.crates-io]` in the root `Cargo.toml`.

Local change: `protocol/openai/common.rs` maps `audio/mp4`, `audio/m4a`,
`audio/x-m4a`, `audio/aac`, `audio/webm` and `audio/opus` to an `input_audio`
format for OpenAI chat completions. Upstream only maps wav/mp3/ogg/flac and
silently drops any other audio, so AFFiNE's m4a transcript slices never reached
OpenAI-compatible endpoints (e.g. a local speech-to-text server).

Remove this directory and the `[patch.crates-io]` entry once upstream ships an
equivalent change.
