# REYMARC SOUNDBOARD PRO — GitHub Auto-Scan Edition

Upload audio files directly into one `assets/` folder. The soundboard scans that folder through the GitHub Contents API and creates sound pads automatically. You do not need to edit `sounds.json` or any manifest.

## Repository structure

```text
REYMARC-SOUNDBOARD-PRO/
├── index.html
└── assets/
    ├── intro.mp3
    ├── applause.mp3
    ├── drumroll.mp3
    ├── buzzer.mp3
    └── awarding.mp3
```

## Add audio files

1. Open your GitHub repository.
2. Open the `assets` folder.
3. Choose **Add file → Upload files**.
4. Upload MP3/WAV/OGG/M4A and other browser-compatible audio files directly into `assets/`.
5. Commit changes.
6. Open the soundboard and click **Connect / Refresh GitHub** (or refresh the page). New audio files are detected automatically.

The first time, enter your public repository as `GITHUB-USERNAME/REPOSITORY-NAME` or paste its GitHub URL. The app remembers this repository in that browser.

## GitHub Pages deployment

1. Upload `index.html` and the `assets/` folder to the repository root.
2. Go to **Settings → Pages**.
3. Choose **Deploy from a branch**, branch `main`, folder `/(root)`, and Save.
4. Open `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.

## How scanning works

- The browser calls GitHub's public Contents API to list files directly inside `assets/`.
- No personal access token is needed for a public repository.
- Only files directly inside `assets/` are scanned; subfolders are intentionally not used.
- Filenames become the initial sound-pad labels.
- All sounds initially appear in the `Sounds` category. You can customize labels, categories and shortcuts from each sound's options menu; custom settings are saved in that browser.
- Sound banks can be created and assigned from the interface.
- New files appear after refreshing the library.

## Important limitations

- The repository must be public for token-free scanning.
- GitHub API rate limits apply; this is intended for normal event use, not high-volume repeated scans.
- GitHub Pages is static hosting. Uploading/removing audio is done in GitHub, not through the soundboard.
- GitHub repository files and Pages bandwidth have practical limits. Keep audio reasonably compressed and use only audio you have permission to distribute.
- MP3 and WAV are recommended for broad browser compatibility.
