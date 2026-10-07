# Quantum Resistant Solana Protocol

Landing page for QRSP, a post-quantum lattice signature layer for Solana accounts.

`index.html` is a single self-contained file. Open it directly in a browser, or
serve the directory:

```
python3 -m http.server 8000
```

The only external request is the Google Fonts stylesheet (Chakra Petch,
IBM Plex Mono); everything else — styles, scripts, the animated lattice
canvas — is inline.

## Content note

The page presents QRSP as a working protocol, with devnet figures and a CLI
transcript. Those numbers are illustrative. The cryptographic constraints it is
built around are real:

- Solana caps a transaction at **1232 bytes** (1280-byte IPv6 MTU less 48 bytes of headers).
- Ed25519 signatures are 64 bytes. ML-DSA-65 (FIPS 204) is 3309 bytes, so a
  post-quantum signature cannot ride in a single packet.
- Falcon-512 at 666 bytes does fit, which is why the design uses it as a fallback.

Do not treat the page as an audited specification.
