<p align='center'><img src="assets/banner.png" alt="Roblox Auto-Player banner"></p>

<p align='center'>
  <strong>Same sheets, same notation, now it actually runs on a Mac.</strong>
</p>

***

<!--
  Swap YOUR_USERNAME/YOUR_REPO once this is pushed, or just delete the whole
  badges block below if you can't be bothered with shields.io right now.
-->
<p align='center'>
  <a href='https://github.com/YOUR_USERNAME/YOUR_REPO/releases/latest'><img alt="Badge" src="https://img.shields.io/github/v/release/YOUR_USERNAME/YOUR_REPO?include_prereleases&sort=date&display_name=release&label=Latest%20release&color=00bb00"></a>
  <a href='https://github.com/YOUR_USERNAME/YOUR_REPO/releases/'><img alt="Badge" src="https://img.shields.io/github/downloads/YOUR_USERNAME/YOUR_REPO/total?label=Download&color=00bb00"></a>
  <a href='https://github.com/YOUR_USERNAME/YOUR_REPO/issues'><img alt="Badge" src="https://img.shields.io/github/issues-raw/YOUR_USERNAME/YOUR_REPO?label=Issues&color=yellow"></a>
  <img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/YOUR_USERNAME/YOUR_REPO?label=Commit%20activity">
</p>
<p align='center'>
  <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/YOUR_USERNAME/YOUR_REPO?style=social">&nbsp;
  <img alt="GitHub forks" src="https://img.shields.io/github/forks/YOUR_USERNAME/YOUR_REPO?style=social">&nbsp;
</p>

Paste a sheet, hit play, it types the notes into Roblox for you. This is just the Mac port of
[ml3czus' Auto-player](https://github.com/goog-company/ml3czus-autoplayer) — same sheets work,
same notation, I just rebuilt the guts in Electron since the original's AHK core only runs on
Windows.

## How to make sheets / how to use it

Same notation as the original, so if you already know it you already know it:

- `[abc]` is a chord — those keys get sent together
- `-` is a short rest
- `|`, `/`, `\` are all a longer rest
- anything else is just a single note

`Key delay` and `Pause delay` can either be set inside the sheet itself (`# Key delay: 40`,
`# Pause delay: 100`) or overridden from the Options menu in the app.

Keystrokes go out through macOS's own `System Events`, so there's no driver to install, just an
Accessibility permission to grant — see below.

## Setup

1. Get [Node.js](https://nodejs.org) if you don't already have it.
2. In this folder:
   ```
   npm install
   npm start
   ```
3. First time it tries to send a key, macOS will ask for Accessibility permission. Give it to
   whatever's asking (Terminal, or "Electron" in dev). If the prompt doesn't show up, go add it
   yourself: `System Settings → Privacy & Security → Accessibility`. You'll have to do this again
   once you build the packaged `.app`, since that's a different binary than the dev one.

## Using it

1. Open Roblox, get into the instrument.
2. Paste a sheet in, or load a `.txt` from the File menu.
3. **F4** plays, **F6** pauses/resumes, **F7** stops. These are global hotkeys so they work even
   with Roblox focused. Hold F6/F7 down instead of tapping — a quick tap can occasionally get
   eaten by macOS before it reaches the app.
4. Tab away from Roblox (or open chat) and it auto-pauses, then picks back up once Roblox's
   focused again.

## Download

Grab it from the Releases tab, source is in Code. If your AV flags it, it's not malicious, it's
just an unsigned Electron app talking to `System Events`, which looks sketchy to a scanner that's
never seen it before.

## Credit

Original Windows version by [ml3czus](https://github.com/goog-company/ml3czus-autoplayer).
Banner art by my friend, who clearly has a future in this.
