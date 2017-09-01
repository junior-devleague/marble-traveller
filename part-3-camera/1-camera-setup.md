# Setting up the Camera?

## Introduction
By default, Unity has a Main Camera set up for us. Let's tweak the settings to have this camera follow our player!

## Changing Camera Perspective

To change the camera perspective, complete the following.
1. Select the Main Camera in the Hierarchy view.
2. In the Inspector, move the camera 10 up and looking 45 degrees downwards. Position Y = 10, Rotation X = 45.
3. Make the Main Camera a child of the Player by dragging the Main Camera in the Hierarchy view on to the Player Object. This is a general third person set up. Test it out!

*Wait, what's going on??! As you move the player, the camera moves (and rotates) with it! But this is not what we want. We want the camera to stay in a relatively fixed position away from the player from a certain distance.**

4. Something isn't right. Detach the camera from the player object by dragging the camera outside of the player object and onto the Hierarchy view window.

5. Actually, we will need a script for our camera to control it! 
