# TLS Certificate Decoder

Decode an X.509 / TLS certificate or a whole chain — subject, SANs, issuer, validity, key type, extensions and fingerprints. Hand-written DER parser, nothing leaves your browser.

**Live:** <https://cert-decoder.slippylabs.com/>

## What it does

- Paste a PEM certificate — or a whole chain — and read what is actually in it.
- Subject and issuer, validity dates, subject alternative names, key type and size.
- Extensions, key usage, and SHA-1 / SHA-256 fingerprints.

## How it works

The DER parser is hand-written: it walks the ASN.1 tag-length-value structure of the certificate directly rather than leaning on a crypto library, which is what lets the whole thing be one static page with nothing to install and nothing to upload. A certificate is not usually secret, but a private chain you are debugging at 2am should still not need to be pasted into someone else's server.

## Run it locally

A static site. No build step, no package manager, no dependencies:

```
git clone git@github.com:slippylabs/cert-decoder.slippylabs.com.git
cd cert-decoder.slippylabs.com
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

---

Part of [Slippy Labs](https://slippylabs.com). Every tool is indexed at
[projects.slippylabs.com](https://projects.slippylabs.com).
