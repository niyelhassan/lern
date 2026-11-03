# lern

Standalone landing page and product walkthrough. Serve this directory with any static host; no runtime framework or build step is required.

```sh
python3 -m http.server 4323 --bind 127.0.0.1
```

Open `http://127.0.0.1:4323/`. Get started opens `onboarding.html`, a four-step video walkthrough followed by the existing usage notes. This repository is the presentation site; the lesson generator lives at https://github.com/niyelhassan/edd.

The original design uses Tailwind 3 utilities, now compiled into the local `utilities.css` so visitors do not download a browser-side CSS compiler. If utility classes change, regenerate it with:

```sh
npx --yes --package tailwindcss@3.4.19 tailwindcss -i ./utilities.input.css -o ./utilities.css --content './index.html,./onboarding.html' --minify
```

`media/` contains four silent demo clips, encoded as H.264/yuv420p at the original 1436×1080 resolution, with MP4 fast-start metadata. Only the active walkthrough step loads its clip. Posters keep the layout stable while media loads. Playback controls remain available; reduced-motion preferences prevent autoplay. The full source recording remains in Git history.
