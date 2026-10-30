# REYMARC SOUNDBOARD PRO — GitHub Edition

An offline-friendly, static soundboard that loads its online audio library from `sounds.json` and audio files stored in this repository. No backend or database is required.

## Repository structure

```text
REYMARC-SOUNDBOARD-PRO/
├── index.html
├── sounds.json
├── README.md
└── assets/
    └── sounds/
        ├── opening/
        ├── sound-effects/
        ├── games/
        ├── transitions/
        └── awarding/
```

## Add songs / sound effects

1. Open the repository on GitHub.
2. Upload each audio file into the correct folder under `assets/sounds/`.
3. Edit `sounds.json` and add an entry for every uploaded file.
4. Commit the changes. GitHub Pages will publish the updated library.

Example `sounds.json`:

```json
{
  "version": 1,
  "banks": ["All Sounds", "Opening", "Sound Effects", "Games", "Transitions", "Awarding"],
  "settings": { "playMode": "both" },
  "sounds": [
    {
      "name": "Opening Intro",
      "path": "assets/sounds/opening/intro.mp3",
      "category": "Opening",
      "banks": ["Opening"],
      "shortcut": "1"
    },
    {
      "name": "Applause",
      "path": "assets/sounds/sound-effects/applause.mp3",
      "category": "Sound Effects",
      "banks": ["Sound Effects"],
      "shortcut": "2"
    }
  ]
}
```

**Important:** `path` is relative to the repository root and is case-sensitive. The file name and path must match exactly. Supported playback depends on the visitor's browser; MP3 and WAV are the safest choices.

## Publish with GitHub Pages

1. Create a GitHub repository named `REYMARC-SOUNDBOARD-PRO`.
2. Upload all files and folders from this package to the repository root (so `index.html` is at the top level).
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch **main** and folder **/(root)**, then Save.
6. Wait for GitHub Pages to publish. Your site will be available at:
   `https://YOUR-GITHUB-USERNAME.github.io/REYMARC-SOUNDBOARD-PRO/`

When opened from GitHub Pages, the app automatically fetches `sounds.json`. The **Load Online Library** button lets you reload it after publishing new sounds.

## Notes and limitations

- This is GitHub-managed: add/remove audio files in the repository and maintain their entries in `sounds.json`.
- The browser cannot list repository folders automatically on its own; the manifest is the index that tells the app which sounds exist.
- Local folder loading remains available as a fallback.
- GitHub Pages is static hosting. There is no website upload/delete interface and no user login.
- Keep repository size and bandwidth in mind. GitHub recommends keeping repositories reasonably small; avoid large audio libraries or high-traffic media hosting. Do not upload copyrighted music unless you have permission.
- Browser local storage can remember some settings, but the browser still needs network access to fetch the online audio files.
