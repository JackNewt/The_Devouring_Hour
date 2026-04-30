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





