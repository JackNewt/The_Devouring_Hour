Date:
2026-09-11

Summary:
Reworked and condensed the player inventory system, adding support for interactive items and collectible notes, reusable inventory slot widgets, contextual inventory actions, UI-focused input handling, and additional debugging controls.

Changes Made:

- Reworked the inventory system to use dedicated inventory data for both items and notes.
- Added support for collectible notes alongside standard inventory items.
- Added unique `Name` IDs to inventory entries for more reliable lookup, removal, and future gameplay checks.
- Added inventory functions for:
  - Adding items.
  - Removing items by ID.
  - Adding notes.
  - Removing notes by ID.
- Added a reusable `WBP_InventorySlot` widget capable of representing both items and notes.
- Added slot initialization logic for:
  - Standard inventory items.
  - Collectible notes.
- Added item/note type tracking through an inventory slot type enum.
- Added contextual action menus to inventory slots.
- Added contextual item actions for:
  - Equip.
  - Unequip.
  - Remove.
- Added contextual note actions for:
  - Read.
  - Remove.
- Added logic to ensure only one inventory slot action menu can be open at a time.
- Added logic to automatically close the previous slot menu when another inventory entry is selected.
- Added logic to close inventory action menus after performing an action or removing an entry.
- Added background-click handling so clicking empty inventory space dismisses the currently open action menu.
- Added a centralized `RefreshInventory` system intended to rebuild the item and note UI from the underlying inventory arrays instead of manually tracking individual UI children.
- Began restructuring inventory responsibilities so `BP_InventoryComponent` manages inventory data while `WBP_InGameMenu` manages inventory presentation.
- Added a debug menu button for manually restoring/re-enabling player movement during development. (Especially useful now after the game starts and the movement is locked due to the beginning sequence being added)

Bugs:
- Tab could be intercepted by UMG's keyboard-navigation behavior after interacting with inventory buttons. Addressed by preventing mouse-driven inventory buttons from taking keyboard focus. This means keyboard cannot be used with the inventory. If we want that, we might want to change the keybind to open it from tab to something else

Additional Notes:
- The inventory system is still under active development and does not yet represent the final item/equipment implementation.
- Items and notes currently remain separate data types but share the reusable `WBP_InventorySlot` presentation layer.
- The contextual inventory menu is designed to support additional actions later without requiring separate UI implementations for every inventory type.
- The current inventory refresh approach is intended to make the underlying inventory arrays the source of truth, allowing the UI to be rebuilt whenever inventory data changes.
- Equipment functionality is being structured so equipped items can eventually be tracked independently of inventory storage.
- The new debug movement control is intended for development/testing and may be removed or replaced once player input and UI transitions are fully stable.


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
