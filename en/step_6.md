## Detecting Santa

Now that you are ready, having tested your PIR Motion Sensor and having created your Santa sprite, it is time to write your program.
{:class="blockdata"}
Here is the basic idea of your algorithm:
  - When the flag is clicked `forever`{:class="blockcontrol"}
  - Check to see if gpio 4 is high
  - If it is:
    - Show your sprite
	- Set it's size to fill the screen
	- Play a loud noise
	- Wait for the duration of the sound
	- Reduce it's size back to normal
  - If it isn't:
    - Hide the sprite
	
- Now create this algorithm in Scratch. If you don't know how to use sounds in Scratch, then have a look at the section below. If you get really stuck you can use the hints.

[[[generic-scratch-sound-from-library]]]

--- hints --- --- hint ---
All your code will need to be place within a `forever`{:class="blockcontrol"} loop. You can then use an `if <  > then else`{:class="blockcontrol"} block to check if the pin is high or low, and carry out the actions.
--- /hint --- --- hint ---
Here's a all the blocks you might need to use:
![random](images/tile_0.png)
--- /hint --- --- hint ---
Here's what your finished script should look like:
![complete](images/complete.png)
--- /hint --- --- /hints ---
