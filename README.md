# Kumo CSS accessibility review evidence

Recordings use real Kumo source components. Before is upstream commit `a39b1a293a0d7bcd8800c81e3ffda79c4bdf8ef9`; after is the corresponding isolated fix branch. Chromium 143 (Playwright 1.57), macOS, device scale factor 1.

## Dialog scrolling

Identical eight-field form and wheel gestures before and after. The after recording also clicks Save settings. The final action is below the viewport before the fix and reachable by scrolling after it.

- [Desktop comparison — before left, after right](dialog-desktop-comparison.mp4) (800 × 500 per panel)
- [Phone comparison — before left, after right](dialog-phone-comparison.mp4) (390 × 600 per panel)
- Desktop: [before](dialog-desktop-before.mp4), [after](dialog-desktop-after.mp4)
- Phone: [before](dialog-phone-before.mp4), [after](dialog-phone-after.mp4)
- [Measured geometry after scrolling](measurements.json)

These are viewport recordings, not physical device or mobile keyboard tests. Dialog titles and actions scroll with the content; this change does not introduce sticky sections.

## Forced-color focus

Keyboard Tab navigation with Chromium forced-color emulation. This emulates the CSS media feature; it is not a native Windows high-contrast test.

- [Before](focus-before.mp4)
- [After](focus-after.mp4)
- Focused button: [before](focus-before.png), [after](focus-after.png)

The product branches contain the regression tests and changesets. This evidence branch keeps recordings out of their package diffs.
