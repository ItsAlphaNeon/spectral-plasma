# Spectral Plasma

(This was created for personal use completely by Claude. Its only public for my own convienence.)

Generative plasma wallpapers coloured by real atomic emission spectra. Pick an element, mix several, or paste a NIST line list. Its discrete emission lines become the palette of a glowing, seamlessly looping plasma.

Everything is in one file, `index.html`. Open it in Chrome or Safari. There's no build step or install, and it needs WebGL 2.

## How the colour works

Each line's wavelength is mapped to its colour on the CIE 1931 spectral locus. An excitation setting applies a Boltzmann-like factor, so cool gas favours low-energy red lines and hot gas lights up the blue and violet ones. A separation field lets individual lines claim their own regions.

**Sources:** 24 elements, plus an H II region, an aurora and the solar chromosphere.
**Forms:** Nebula, Tendrils, Aurora and Field lines.

## Exports

| Export | For |
|---|---|
| PNG still | Static wallpaper at any size, including presets for current Mac displays up to 6016×3384 |
| MP4 loop | Video wallpaper apps. Rendered frame by frame as H.264, and the loop is seamless |
| Wallpaper Engine, pre-rendered video (default) | Zip containing an H.264 `plasma.mp4` loop, `project.json` and a preview. Wallpaper Engine just decodes the video, which is much lighter than the live shader. Unzip it into a folder inside `wallpaper_engine\projects\myprojects` |
| Wallpaper Engine, live shader | Zip containing `index.html`, `project.json` and a preview, with settings editable in Wallpaper Engine. Choose *Open Wallpaper › Open from File* and pick `index.html` |
| Live HTML | Web-page wallpaper apps, such as Plash on macOS or Lively on Windows |

## Settings codes

Every look has a code like `SP1.eyJlbGVtZW50cyI6…`, which is base64url-encoded JSON. Copy it from the **Settings code** section. You can load it:

- by pasting it into the same field on another device
- by pasting it into the *Settings code* property of an exported Wallpaper Engine wallpaper
- by adding it after `#` at the end of the app's or a Live HTML file's URL

The app's own URL hash always holds the current code, so a bookmark saves a look.

## Keys

`H` hide controls · `Space` pause · `R` new seed · `S` surprise · `F` fullscreen

## Notes

- The MP4 export loads [mp4-muxer](https://www.npmjs.com/package/mp4-muxer) from jsDelivr the first time. Offline, it falls back to recording in real time.
- Wavelengths come from the NIST Atomic Spectra Database. Relative intensities are approximate and normalised per element; paste a NIST table for exact values.
- Live rendering is GPU-heavy. For an always-on wallpaper, use a pre-rendered video, or lower *Render scale* and the live frame cap.
- Pre-rendered videos use the export *Resolution*, *Video frame rate* and *Loop length*. Size them to the screen; 24–30 fps is plenty for slow plasma.
