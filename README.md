# Timer PWA

Installable fullscreen countdown timer for mobile and desktop browsers.

## Features

- Custom countdown duration
- Fullscreen mode
- Screen Wake Lock support
- Vibration and reset sound feedback
- Beeps during the final 5 seconds
- Alarm and flashing background at 0
- White particle bursts from the RESET button
- Offline-capable PWA
- Installable from Android Chrome when served over HTTPS

## Repository structure

```text
.
├── .github/
│   └── workflows/
│       └── pages.yml
├── .nojekyll
├── icon-192.png
├── icon-512.png
├── index.html
├── manifest.webmanifest
├── sw.js
└── README.md
```

All application URLs are relative, so the PWA works both on a user/organization Pages site and on a project Pages URL such as:

```text
https://USERNAME.github.io/REPOSITORY/
```

## Deploy to GitHub Pages

1. Create a new GitHub repository, for example `timer-pwa`.
2. Upload or commit all files from this folder to the repository root.
3. Make sure the default branch is named `main`.
4. On GitHub, open **Settings → Pages**.
5. Under **Build and deployment → Source**, select **GitHub Actions**.
6. Push a commit to `main`, or open **Actions → Deploy static site to GitHub Pages → Run workflow**.
7. When deployment finishes, open the Pages URL shown by GitHub.

For a repository named `timer-pwa`, the normal project URL is:

```text
https://USERNAME.github.io/timer-pwa/
```

## Install on Android Chrome

1. Open the deployed HTTPS URL in Chrome.
2. Use Chrome's menu and choose **Install app** or **Add to Home screen**.
3. Launch it from the home screen or app launcher.

The first interaction with START or RESET enables browser-gated features such as fullscreen, audio, vibration and wake lock when the device/browser supports them.

## Updating the PWA

Push changes to `main`. GitHub Actions redeploys the site automatically. The service worker cache name in `sw.js` should be bumped when changing cached assets so already-installed clients fetch the new version promptly.
