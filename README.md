# JWT Decoder

A tiny, single-file, fully-offline tool for decoding JSON Web Tokens (JWTs) in the browser. No build step, no dependencies, no network calls — paste a token and read its contents.

🔗 **Live demo:** https://attiq178.github.io/JWT-Decoder/

## Features

- **Two-step decode** — automatically detects the input format:
  - A **base64-wrapped JWT** is base64-decoded first to reveal the JWT, then decoded.
  - A **raw JWT** (`eyJ...`) is decoded directly.
  - A note above the output tells you which path was taken.
- **base64url-aware** — handles the `-`/`_` alphabet and missing `=` padding, and decodes UTF-8 payloads correctly.
- **Header / Payload / Signature** shown in separate panels; the signature is shown raw (it's a binary cryptographic signature, not JSON).
- **Readable claims** — renders `iat`, `nbf`, and `exp` as local dates, with a `VALID` / `EXPIRED` badge.
- **Copy buttons** on every panel.
- **URL parameter** — pass a token directly: `?token=<jwt-or-base64>`.
- **100% client-side** — tokens are never sent anywhere.

## Usage

1. Open the [live demo](https://attiq178.github.io/JWT-Decoder/), or download `index.html` and double-click it.
2. Paste a JWT or a base64-wrapped JWT into the box (or click **Load sample**).
3. The header, payload, and signature are decoded instantly.

## Security note

This tool only **decodes** tokens — it does **not** verify signatures. A JWT's payload is not encrypted, so never paste production tokens into any tool you don't fully trust. This page runs entirely offline, but as a habit, treat tokens like passwords.

## License

[MIT](LICENSE)
