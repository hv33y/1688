# 1688 Link Cleaner & Converter

A minimal, single-page web app that extracts raw 1688 app share messages and converts them into clean, mobile links (`m.1688.com`) optimized for shopping agents like **CNfans**.

### 🔗 Live Tool
Try it here: **[hv33y.github.io/1688](https://hv33y.github.io/1688/)**

---

## What It Does

* **Strips the Mess:** You can paste a full, cluttered share string copied directly from the 1688 app. The tool automatically separates the URL from Chinese characters, emojis, and tracking junk.
* **Resolves App Links:** For short/QR links (`qr.1688.com`), it routes through a public CORS proxy to grab the final destination URL and extract the actual numerical item ID.
* **Agent-Ready Output:** Formats everything into standard `https://m.1688.com/offer/[ID].html` so it parses perfectly when pasted into CNfans or similar agents.
* **Pure Frontend:** Zero database, zero logging, and zero tracking. It runs entirely in the browser using custom CSS properties and client-side JavaScript.

---

## Quick Setup

Since this is a self-contained static page, it requires no backend or build steps.

1. Drop `index.html` into the root of your repository.
2. Go to your GitHub repository settings -> **Pages**.
3. Set the build source to your main branch root and save.

---

## Examples

**Raw App Input:**
> 7另 %aD3dxxx %达 .hTtp://qr.1688.com/share/html/detail/index.html?trShareId=xxxx&targetId=1234567890 

**Cleaned Output:**
> `https://m.1688.com/offer/1234567890.html`

---

## Limitations

* **Proxy Reliance:** Un-shortening encrypted `qr.1688.com` links relies on `corsproxy.io`. If 1688 hits the proxy with heavy rate limits or CAPTCHAs, the script will throw a connection error, requiring manual URL extraction.
