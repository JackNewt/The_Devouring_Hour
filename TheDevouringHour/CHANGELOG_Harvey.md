Harvey Wheeler - 9/4

---

#### \- Summary -

Added more tutorial branches, almost functioning properly.



##### \- Changes Made -

* Added branches corresponding to info recaps ("Could you repeat something?")
* Dialogue is empty for these branches, but they loop back to the dialog before.


##### \- Bugs -

* Figured out why buttons were not showing up. Just need to add more buttons than three.


##### \- Additional Notes -

* I really wanna get this part done ASAP so I can actually start making the game part.
* Will work on dispenser afterwards.

Harvey Wheeler - 9/3

---

#### \- Summary -

Added more tutorial branches, but not functioning properly.



##### \- Changes Made -

* Added branches corresponding to info recaps ("Could you repeat something?")
* Dialogue is empty for these branches, but they loop back to the dialog before.


##### \- Bugs -

* For some reason, the option to skip repeating info ("I understand") does not show up, nor any info repeat choices besides the Analyzer. Loops between the two, cannot exit the dialog. Help


##### \- Additional Notes -

* I really wanna get this part done ASAP so I can actually start making the game part.
* Will fix debug menu after.


Harvey Wheeler - 9/1

---

#### \- Summary -

Added more tutorial cameras.



##### \- Changes Made -

* Added cameras for generator, generator meter, boiler, and computer.
* All cameras and dialogue added to tutorial sequence.


##### \- Bugs -

* Need to fix tutorial ending. Unable to close phone dialog.


##### \- Additional Notes -

* Will continue on the tutorial.
* Will fix debug menu after.


Harvey Wheeler - 8/26

---

#### \- Summary -

Fixed tutorial camera switching.



##### \- Changes Made -

* Added unique tag to each tutorial camera. Instead of pulling all with the same tag and sorting through an array, each subphase just pulls each individual tag.
* Camera snaps instantly instead of blending.





##### \- Bugs -

* N/A



##### \- Additional Notes -

* Will continue on the tutorial.


Harvey Wheeler - 8/26

---

#### \- Summary -

Implemented tutorial camera switching, up through patient.



##### \- Changes Made -

* Added cameras angled at each piece of machinery.
* Starting tutorial at phone now triggers 1.1.3-1.1.11, in a chain.
* Camera swaps with each subphase.





##### \- Bugs -

* When pulling all cameras from the world, it puts them into an array with an unknown order. Causes swapping to incorrect cameras. Working on it



##### \- Additional Notes -

* Do we have the generator?


Harvey Wheeler - 7/11
---

#### 

##### \- Summary -

Implemented dialogue system into the phone.



##### \- Changes Made -

* Dialogue now begins when answering a phone call.
* Edited Dialogue\_data to include a new trigger: "ChangeGameState"

  * Currently only set up to change subphase, more in near future
* Now, subphase 3 will not begin unless the correct dialogue options are chosen
* More dialogue can be easily implemented with whatever game state triggers we want





##### \- Bugs -

* Camera control not returned to player when dialog is closed, must press E again. Unsure why.



##### \- Additional Notes -

* Still waiting on the go-ahead with the generator. Will ask Joseph





### Harvey Wheeler - 7/3

#### 

##### \- Summary -

Added a camera which locks on to the phone while a call is occurring.



##### \- Changes Made -

* Added a camera which locks on to the phone while a call is occurring.
* Locks player controls while camera is locked
* Will automatically revert camera when call finishes
* Can also be done early by interacting again



##### \- Bugs -

* None



##### \- Additional Notes -

* Next, I plan on locking the camera to the phone when calls are in progress. Looking at code for keypad for reference.
* After first phone call, hoping to enable the generator.
* Possibly implement dialogue system into phone?



### Harvey Wheeler - 6/12

#### 

##### \- Summary -

Added global variables for stage, phase, and subphase.



##### \- Changes Made -

* Added global variables for stage, phase, and subphase.
* Created functions for updating stage, phase, and subphase variables.
* Created function for triggering progression events based on game state.
* Phone now rings after lights are turned on (state 1.1.2 is triggered).
* State 1.1.3 triggered when first phone call is answered. Following event to be added soon.



##### \- Bugs -

* None



##### \- Additional Notes -

* Next, I plan on locking the camera to the phone when calls are in progress. Looking at code for keypad for reference.
* After first phone call, hoping to enable the generator.
* Possibly implement dialogue system into phone?



### Harvey Wheeler - 5/9

#### 

##### \- Summary -

Restructured/Renamed all files for clarity. Removed some redundant files.



##### \- Changes Made -

* Added appropriate prefixes to all files that were missing them, based on asset type.
* Reorganized assets/folders to group like with like.
* Removed all but one interaction Blueprint Interface.
* Updated the phone and light switch to use the same interaction blueprint interface, with an interaction prompt and everything.



##### \- Bugs -

* Some of the empty folders are not able to be deleted. Can be safely ignored, I'll see what I can do about them.



##### \- Additional Notes -

* I wasn't entirely sure which assets were made by who, so I avoided adding name suffixes at this point. Should be able to add them without issue in the future. It would be great if you all could rename them yourselves maybe? :)
* Please let me know if I need to change anything for better clarity, I was kinda just freeballing it.

### 

### Jaqlyn Crow - 4/28

##### 

##### \- Summary -

This is the first Changelog for our in house team. I expect everyone to add a section to this file before pushing your changes to the repository.



Please be as detailed as possible to give your teammates the best chance of utilizing this information.



Please include 4 sections, a brief summary of what you changed and your intentions, a list of the exact changes in more detail, any unresolved bugs you encountered, and any additional notes or requests you may have at the bottom.



I will set the standard for what I expect to see below with my changes as of 4/28.



##### \- Changes Made -

* Added a sixth spotlight to the Laboratory. Updated both blueprints that care about the spotlights to include it.
* Moved the sixth light to better illuminate the Generator, i.e. slightly closer to the center of the room. Is not final placement.
* Disabled certain rendering features including Ambient Occlusion and Auto Exposure, as they don't fit the style of our game.
* ###### **Modified the Generator Blueprint**

  * Added a variable for whether the Lever is Flipped up or down
  * Modified timer related variables to Read more in line with actual functionality (Default and Current Energy Level Respectively)
  * Modified the timer system to tick up when the lever is flipped up and tick down when the lever is flipped down
  * Changed Blackouts to occur when the timer reaches 20 (it's max) in addition to 0.

    * Generater checks after incrementing the energy level if the level is between 1 and 19. If not, the Blackout will occur.
  * **NOTE** : *There is currently no functionality to flip the lever up and change the lever state to active. Pressing E on the lever still just resets the value to 0 and now causes a Blackout.*

    * Fixed this!! Flip Functionality Works now!
    * Clicking on the generator will only call the reset the generator if the power is failing.
    * The Countdown now checks to see what the Lever State is before deciding whether to increment to Energy Level up or down.

##### 

##### \- Bugs -

* I can't pick up the phone, please investigate.



##### \- Additional Notes -

Please refer to the Modeling Notes Document in regards to the changes needed to finish implementing what I worked on today.



\# Olive Change Log

\## Changes Made (02/11/2026)

\- Added 3 new BluePrints

&#x20; - BP\_InventoryComponent - Handles tracking the current item, adding, removing, cycling next, cycling previous item

&#x20; - S\_InventoryItem - Structure that breaks into the item name, item description, and item icon

&#x20; - WBP\_InventoryClipboard - the visual clipboard (VERY PRIMATIVE!!!! Will be updated to look better soon)



\- Edits to BP\_FirstPersonCharacter

&#x20; - ToggleInventory Logic

&#x20; - CycleInventory Logic

&#x20; - Inventory test items (for demo purposes)



\- Next update, looking to have "pick-upable" objects to add to inventory

\- Some tweaks to clipboard UI widget so it doesn't look as ugly and take up the entire screen (more clipboard-like)



\## Changes Made (02/18/2026)

\- Added new BluePrint Actor 'BP\_PickupableBase'

&#x20; - The base is a duplicate of 'BP\_InteractableBase', is detected by the first person character in the same way

&#x20;- Created new function 'UpdateHeldItem' in BP\_FirstPersonCharacter

&#x20;  - This function handles setting the correct static mesh for the currently held item

\- Updated CycleInventory logic in BP\_FirstPersonCharacter EventGraph to include UpdateHeldItem when cycling

&#x20; - Cycling through the clipboard using Q and E will change the player's currently held item respective to what is displayed on the clipboard

&#x20; - ToggleInventory Logic also includes UpdateHeldItem so that held item is shown regardless of if menu is up or not

\- Added input mapping to key H to toggle currently held item visible/hidden



\## Changes Made (02/24/2026)

A skeleton dialog system that supports both linear and branching conversations. Players can interact with interactable objects (will be NPCs) and make choices that lead to different dialog paths.



\## Updates



\### 1. S\_DialogData (Structure)

Defines a single dialog entry.

\- \*\*SpeakerName\*\*: Who is speaking

\- \*\*DialogText\*\*: What they say

\- \*\*Responses\*\*: Array of player response options

\- \*\*NextDialogIndices\*\*: Array of dialog indices to jump to for each response



\### 2. WBP\_DialogBox (Widget Blueprint)

The UI that displays dialog on screen.

\- Shows speaker name and dialog text

\- Displays response buttons or continue button based on dialog type

\- Manages dialog flow and progression



\### 3. BP\_DialogueTrigger (Actor Blueprint)

Interactable actor placed in the world that starts dialog.

\- Implements BPI\_Interactable interface

\- Contains DialogSequence array with all dialog entries

\- Spawns dialog widget when player presses E



\## How It Works



\### Linear Dialog

1\. Player interacts with trigger

2\. Dialog displays with Continue button

3\. Clicking Continue advances to next dialog

4\. Ends when reaching the last entry



\### Branching Dialog

1\. Player interacts with trigger

2\. Dialog displays with 1-3 response buttons

3\. Clicking a response jumps to specified dialog index

4\. Can branch to different conversation paths

5\. Ends when reaching a dialog with no next index



Olive Change Log

Changes Made (02/11/2026)



Added 3 new BluePrints



BP\_InventoryComponent - Handles tracking the current item, adding, removing, cycling next, cycling previous item

S\_InventoryItem - Structure that breaks into the item name, item description, and item icon

WBP\_InventoryClipboard - the visual clipboard (VERY PRIMATIVE!!!! Will be updated to look better soon)





Edits to BP\_FirstPersonCharacter



ToggleInventory Logic

CycleInventory Logic

Inventory test items (for demo purposes)





Next update, looking to have "pick-upable" objects to add to inventory

Some tweaks to clipboard UI widget so it doesn't look as ugly and take up the entire screen (more clipboard-like)



\## Changes Made (02/18/2026)



Added new BluePrint Actor 'BP\_PickupableBase'



The base is a duplicate of 'BP\_InteractableBase', is detected by the first person character in the same way





Created new function 'UpdateHeldItem' in BP\_FirstPersonCharacter



This function handles setting the correct static mesh for the currently held item





Updated CycleInventory logic in BP\_FirstPersonCharacter EventGraph to include UpdateHeldItem when cycling



Cycling through the clipboard using Q and E will change the player's currently held item respective to what is displayed on the clipboard

ToggleInventory Logic also includes UpdateHeldItem so that held item is shown regardless of if menu is up or not





Added input mapping to key H to toggle currently held item visible/hidden



\## Changes Made (02/24/2026)

A skeleton dialog system that supports both linear and branching conversations. Players can interact with interactable objects (will be NPCs) and make choices that lead to different dialog paths.

Updates

1\. S\_DialogData (Structure)

Defines a single dialog entry.



SpeakerName: Who is speaking

DialogText: What they say

Responses: Array of player response options

NextDialogIndices: Array of dialog indices to jump to for each response



2\. WBP\_DialogBox (Widget Blueprint)

The UI that displays dialog on screen.



Shows speaker name and dialog text

Displays response buttons or continue button based on dialog type

Manages dialog flow and progression



3\. BP\_DialogueTrigger (Actor Blueprint)

Interactable actor placed in the world that starts dialog.



Implements BPI\_Interactable interface

Contains DialogSequence array with all dialog entries

Spawns dialog widget when player presses E



How It Works

Linear Dialog



Player interacts with trigger

Dialog displays with Continue button

Clicking Continue advances to next dialog

Ends when reaching the last entry



Branching Dialog



Player interacts with trigger

Dialog displays with 1-3 response buttons

Clicking a response jumps to specified dialog index

Can branch to different conversation paths

Ends when reaching a dialog with no next index





\## Changes Made (03/10/2026)

Interactive computer screen system that allows players to interact with in-world UI displays. Players can view monitor screens with clickable interfaces and exit back to gameplay.

Updates

\### 1. BP\_Monitor (Actor Blueprint)

Interactable computer monitor placed in the world.

Components:



MonitorCamera: Camera component for viewing the screen up close

ScreenMesh: Static mesh (SM\_Plane, 100×100cm) displaying the monitor screen

ScreenWidget: Widget component showing MonitorUI in world space (1024×1024 resolution)

UI\_InteractPrompt: Widget showing interact prompt when player looks at monitor



Variables:



InUse (Boolean): Tracks if player is currently viewing the monitor

CachedPlayerController (Player Controller): Stores reference to player controller

CachedViewTarget (Actor): Stores original camera view target before switching

BlendTime (Float): Camera blend duration (default: 0.7 seconds)



OnInteract Event Logic:



Exiting Monitor (InUse = true):



Blend camera back to cached view target

Set input mode to Game Only

Hide mouse cursor

Set InUse to false





Entering Monitor (InUse = false):



Cache player controller and current view target

Activate MonitorCamera component

Blend camera to monitor (Self as view target)

Set input mode to UI Only with widget focus

Show mouse cursor

Set InUse to true



OnViewed Event Logic:



Shows interact prompt briefly when player looks at monitor

Prompt fades after 0.2 seconds



\### 2. MonitorUI (Widget Blueprint)

The UI displayed on the computer screen.

Designer Layout:



Canvas Panel (root) - 1024×1024 resolution

Background (Image): Full-screen background image, exposed as variable

ExitButton (Button): Top-right "X" button to exit monitor view

TestButton (Button): Center test button for color demonstration



Event Graph Logic:



TestButton OnClicked:



Randomly changes Background color between red and blue

Uses Random Bool → Branch → Set Color and Opacity





ExitButton OnClicked:



Gets all BP\_Monitor actors in scene

Calls OnInteract on first monitor to exit view

Uses Get Owning Player Pawn as instigator



\### 3. ScreenWidget Component Configuration

Widget component settings for world-space UI display.

Settings:



Space: World (critical - not Screen space)

Widget Class: MonitorUI

Draw Size: 1024 × 1024 pixels

Transform:



Location: X=1, Y=0, Z=0 (slightly in front of mesh)

Rotation: Yaw=180° (faces outward)

Scale: X=0.1, Y=0.1, Z=1.0 (scales widget to match 100cm mesh)





Visible: Checked

Hidden in Game: Unchecked



\# Jared Change Log

\## - 2026-03-10

\### Added

\- Added new struct for pill PillData for potential future use

&#x20;   - Includes PillName, StatusEffect, and DegradationEffect

\- Added instance editable variables in BP\_Keypad and BP\_Dispenser to connect them

\- Added new custom event "DispensePill" in BP\_Dispenser



\### Changed

\- Made String:String map (ValidCodes) in BP\_KeyPad a String:PillData type

&#x20;   - Changed SubmitInput function and CreateRandomInput event to work with new map type

\- Tweaked OnInteract in BP\_Dispenser to call DispensePill custom event instead

\- Changed SubmitInput function in BP\_Keypad to call DispensePill on the connected BP\_Dispenser

&#x20;



\## - 2026-03-09

\### Changed

\- Fixed BP\_InteractableBase, BP\_PickupableBase, BP\_DialogTrigger

&#x20;   - Added cube back into viewport and resolved collision trace channel issues





\## - 2026-02-24

\### Added

\- New BPI that adds dynamic functionality for using the enter key on different focus-interactable objects

\- Added ValidCodes string -> string map that contains valid codes (keys) that correspond to pills (values)

&#x20;   - Ex. 1234 -> Pill 1

\- Added enter key event in BP\_FirstPersonCharacter

\- Added documentation



\### Changed

\- SubmitInput now prints whether or not the input code corresponds to a pill

\- Put movement and cursor toggling in it's own function "ToggleMovementAndCursor"



\### Removed

\- Removed submit button box collision and on click event





\## - 2026-02-23

\### Added

\- Temporary key pad model

\- Key pad blueprint that

&#x20;   - Toggles camera view from first person to focus on the key pad upon interacting with the blueprint

&#x20;   - Tracks clicks on buttons 1-9 and submit button

&#x20;   - Has a submit button that prints the string of numbers the user input

\- New line trace channel "InteractionTrace" that handles interaction checks



\### Changed

\- Tweaked interaction in FirstPersonCharacter to line trace by new trace channel "InteractionTrace" rather than "Visibility"

\- Updated BP\_InteractableBase to handle collision with new InteractionTrace channel





\## - 2026-02-16

\### Added

\- Inventory system with scrollwheel compatability

\- Data Asset template for making inventory items

\- Added two new functions to Interactable interface

&#x20;   - IsPickup (returns boolean)

&#x20;   - GetItemData (returns Data Asset)

\- Two temporary items (blue key and red box)

\- Clear inventory function that wipes entire inventory

\- Clear inventory item function that removes currently selected item



\### Changed

\- BP\_InteractableBase now takes two instance editable variables

\- Tweaked interaction in FirstPersonCharacter to check if BP\_InteractableBase is also a pickup item

