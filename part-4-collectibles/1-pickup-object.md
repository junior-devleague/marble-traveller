# Creating and Rotating Pickup Objects

## Introduction
Let's create objects that we can collect in our game!

## Create these Collectibles

To create a collectible item, complete the following.

Collectible items can be any shape and size! In the games that we see, collectibles could be in the form of keys, coins, or any other object to help the player progress through a game. Today, we'll keep it simple and use cubes!

1. Create a Cube from the Game Object Menu. Game Object -> 3D Object -> Cube.

![Game Object](https://github.com/junior-devleague/ancient-lands/blob/master/images/gameobject-cube.jpg)

2. Right click on this newly created Cube in the Hierarchy view. Rename the cube 'Pickup'.
3. Focus the view on this object by pressing 'F' for frame current view. Make sure you have the cube selected in your Hierarchy view.
4. We need to make this object look special! Create a new material to make this object have a different color. Go to your Project View and click Create -> Material. Once this is created, drag the material to your object from the Project View to the object in Scene View. 

![New Material](https://github.com/junior-devleague/ancient-lands/blob/master/images/new-material.jpg)

5. Click on your pickup object. In the Inspector Menu's Transform section, scale this object to be smaller (X=0.2, Y=0.2, Z=0.2), and tilt the object by setting its rotation to X = 45, Y = 45, Z = 45 (45 degrees).
6. Now, let's make it rotate! Add a New Script Component to this pickup object.

![New Script](https://github.com/junior-devleague/ancient-lands/blob/master/images/new-script-for-pickup.jpg)

Make sure the language being used is JavaScript. Name this script 'Rotate'.

7. We want to make the object rotate. Since we already set the object's initial rotation, we don't need anything in our Start function. On every update, however, we want to rotate our cube! Type in 'rotate' in the editor, highlight the word, and press CMD + ' to pop up all relevant links.

8. Search for one that says transform.Rotate. In our Update function, we want to use this function which will store a Vector3 to rotate our object's x value by 15 degrees, y value by 30 degrees, and z value by 45 degrees. Thus, we will have to write something like this:

```JavaScript
transform.Rotate(Vector3(15,30,45) * _____________)

```

Fill in the blank! Looking at the examples in the Unity documentation, what will we have to multiply our Vector3 values by?

9. Run your game and see the object rotate!
