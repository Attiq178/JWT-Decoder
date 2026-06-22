# JWT Decoder & Generator

A tiny, single-file, fully-offline tool for **decoding** and **generating** JSON Web Tokens (JWTs) in the browser. No build step, no dependencies, no network calls.

🔗 **Live demo:** https://attiq178.github.io/JWT-Decoder/

## Features

### Decode
- **Two-step decode** — automatically detects the input format:
  - A **base64-wrapped JWT** is base64-decoded first to reveal the JWT, then decoded.
  - A **raw JWT** (`eyJ...`) is decoded directly.
  - A note above the output tells you which path was taken.
- **base64url-aware** — handles the `-`/`_` alphabet and missing `=` padding, and decodes UTF-8 payloads correctly.
- **Header / Payload / Signature** shown in separate panels; the signature is shown raw (it's a binary cryptographic signature, not JSON).
- **Readable claims** — renders `iat`, `nbf`, and `exp` as local dates, with a `VALID` / `EXPIRED` badge.

### Generate
- **Editable, prepopulated payload** — start from a sample claim set, change the values, and sign.
- **HS256 signing** via the Web Crypto API (`crypto.subtle`) using a shared secret — no libraries.
- **Helper buttons** — set `iat = now` and `exp = +5 min` with one click.
- **Optional base64-wrapped output** — also emit the whole token base64-encoded, matching the wrapped form the decoder accepts (full round-trip).

### Everywhere
- **Copy buttons** on every panel.
- **URL parameter** — pass a token directly to the decoder: `?token=<jwt-or-base64>`.
- **100% client-side** — tokens and secrets never leave your browser.

## Usage

1. Open the [live demo](https://attiq178.github.io/JWT-Decoder/), or download `index.html` and double-click it.
2. **Decode:** paste a JWT or base64-wrapped JWT (or click **Load sample**) — header, payload, and signature decode instantly.
3. **Generate:** switch to the **Generate** tab, edit the payload, enter a secret, and click **Generate JWT**.

## Security note

This tool only **decodes** tokens — it does **not** verify signatures. A JWT's payload is not encrypted, so never paste production tokens into any tool you don't fully trust. This page runs entirely offline, but as a habit, treat tokens like passwords.

## License

[MIT](LICENSE)
