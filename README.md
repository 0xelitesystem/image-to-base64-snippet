# Image to Data URI

Convert any image into a base64 data URI you can paste straight into HTML, CSS, or Markdown.

**Live demo:** https://0xelitesystem.github.io/image-to-data-uri/

## Use

1. Open the tool and drop an image on the box, click to browse, or paste one from your clipboard.
2. Pick how you want it wrapped: a raw data URI, a CSS `background-image`, an HTML `<img>` tag, or Markdown.
3. Click **Copy** and paste it wherever you need it.

The panel shows the file type, the original size, the encoded size, and the overhead so you can see exactly what inlining costs. Base64 adds roughly a third to the byte count, so the tool flags images over 1 MB where a normal file is the better choice.

SVG files get an extra option: URL-encode instead of base64. For most vector art the URL-encoded form is smaller, and the tool keeps it lossless so the decoded bytes match the original exactly.

## Why this exists

Most "image to base64" converters upload your file to a server to do a job the browser can do on its own. This one does not. It is a single HTML file with no build step, no dependencies, no CDN, and no network calls. Nothing is uploaded, nothing is logged, and there is no analytics watching you work. Read the whole thing in one sitting, host it yourself, or keep a copy offline. It is MIT licensed, so it is yours to fork.

## Privacy

Everything runs in your browser. The image is read locally with the FileReader API and encoded in memory. No part of your file is ever sent anywhere, because the page makes no network requests at all. You can open your dev tools, load an image, and confirm it: zero requests leave the page.

## Run locally

```
git clone https://github.com/0xelitesystem/image-to-data-uri.git
cd image-to-data-uri
```

Then open `index.html` in any browser. There is nothing to install. If you prefer a local server:

```
python -m http.server
```

and visit http://localhost:8000/.

## Build

No build. It is one self-contained `index.html` with inline CSS and JavaScript. Edit the file, refresh the page, done.

## License

MIT. See [LICENSE](LICENSE).

## Related

- [jwt-inspector](https://github.com/0xelitesystem/jwt-inspector), decode and inspect JSON Web Tokens in the browser.
- [eeat-signals-reference](https://github.com/0xelitesystem/eeat-signals-reference), a plain-language explainer on E-E-A-T signals.
