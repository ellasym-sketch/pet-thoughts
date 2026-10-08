# Pet Thoughts

Take a picture of your pet and find out what it's "thinking". Claude looks at the photo and writes a short, funny monologue in one of six voices, with an optional roast mode. It's for laughs, not science.

## Run it

1. Open `index.html` in Chrome or Safari (double-click it, or right-click > Open With).
2. Open **Setup** and paste an Anthropic API key. Get one at https://console.anthropic.com (API Keys). Add a few dollars of credit under Billing first.
3. Upload a pet photo, pick a voice, and hit **Translate**.

The key is saved only in your browser (localStorage) and is only sent to Anthropic.

## How it's built

Everything is in `index.html`: HTML, CSS and JavaScript, with no build step or dependencies.

- `VOICES`: the six personalities (name, description sent to Claude, loading lines). Add a voice by adding an entry.
- `prompt()`: the instructions sent to Claude, including the roast mode rules.
- `callClaude()`: calls `https://api.anthropic.com/v1/messages` with the photo (resized to 1200px JPEG) and the prompt.
- `MODELS`: the Claude models to try, in order.

## Ideas for next steps

- Put it online (Vercel, Netlify, GitHub Pages) so it works on a phone with the camera.
- Move the API call to a small server so the key isn't in the browser (needed before sharing it publicly).
- Save past translations, or share a translation as an image.
