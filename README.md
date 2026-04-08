# WebGP

A minimal, client-side PGP encryption and decryption tool that runs entirely in the browser. No data is ever sent to a server.

**[Live demo →](https://jimmayu.github.io/webgp/)**

## Features

- Symmetric PGP encryption and decryption using a passphrase
- AES-256 cipher with SHA-512 key derivation (iterated S2K, ~65 million rounds)
- Passphrase verification field to prevent encryption typos
- Dark and light themes
- Key derivation timing display
- No build step, no dependencies to install — open `index.html` and go

## Usage

1. Paste your plaintext (or armored PGP message) into the top field
2. Select **Encrypt** or **Decrypt**
3. Enter your passphrase (and verify it when encrypting)
4. Click the action button
5. Copy the output with **Copy Output**

## Security notes

- All cryptographic operations run locally in your browser via [OpenPGP.js](https://openpgpjs.org/)
- The library uses symmetric encryption (password-based), not public-key cryptography
- The high iteration count makes brute-force attacks significantly more expensive
- For sensitive use, serve the app over HTTPS to prevent script injection

## Running locally

No server required — just open `index.html` directly in any modern browser, or serve it:

```bash
npx serve .
# or
python3 -m http.server
```

## Tech stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 |
| Styles | CSS (custom properties, flexbox) |
| Logic | Vanilla JavaScript (ES2020+) |
| Crypto | [OpenPGP.js v6](https://openpgpjs.org/) |

## License

The application code is released under the [MIT License](LICENSE).  
OpenPGP.js is distributed under the [LGPL-3.0 License](https://www.gnu.org/licenses/lgpl-3.0.html).
