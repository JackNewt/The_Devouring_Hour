Date:
2026-08-29

Summary:
Builds out the interactive desktop UI and introduces the initial page/navigation system for the in-world computer.

Changes Made:
- Added a black-screen/loading state for the desktop startup sequence.
- Added animated Loading... text that begins when the desktop is powered on. (Meant to be built upon)
- Updated world-space Widget Component handling to prevent overlapping widgets from interfering with UI interaction.
- Added a file-selection/home screen with links for:
  - The Analyzer
  - The Pill Dispenser
  - The Patient & Tube
  - The Generator
  - The Boiler
- Added individual WBP pages for desktop applications.
- Added reusable page-switching logic for moving between desktop applications.
- Added shared Back-button handling to return applications to the file-selection screen.
- Added hover effects to desktop file links, including dynamically displayed underlines.
- Imported and configured IBM Plex Mono for a terminal/CLI-style interface.
- Investigated world-space UI ghosting caused by TSR and added a custom widget material configuration to reduce temporal screen bleed.
- Adjusted Widget Component collision behavior to prevent intermittent loss of UI interaction.

Bugs:
- World-space UI showed temporal screen bleed/ghosting when switching pages under TSR. I fixed by changing some settings regarding velocity shaders, but might want to follow up on that

Additional Notes:
- The loading sequence (and everything else visually) is intended to be expanded upon in future work.
- Desktop pages are structured to support continued development of each application.
- TSR/world-space widget rendering may still require additional tuning to fully balance ghosting reduction and UI clarity.
