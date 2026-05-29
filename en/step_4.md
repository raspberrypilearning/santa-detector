## Detecting Santa

Now that you have tested the motion sensor and created your Santa sprite, you're ready to write your program.

Here is what your program should do:
  1. When the flag is clicked
  1. `forever`{:class="block3control"}
  1. Check to see if **GPIO 4** is `high`
	 1. If it is:
		- Show your sprite
		- Set its size to fill the screen
		- Play a loud noise
		- Wait for the duration of the sound
		- Reduce its size back to normal
	 1. If it isn't:
		- Hide the sprite
	
--- hints ---
--- hint ---
Here's what your finished script should look like:
```block3
when flag clicked
set gpio (4 v) to input [pulled low] ::extension
forever
if <gpio (4 v) is [high v] :: extension> then
show
set size to (150)%
play sound [whoop v] until done
set size to (100) %
else
hide
```
--- /hint ---
--- /hints ---

