# Camera Controls

## Introduction
We saw previously that we cannot have the camera as the child of the Player Object. Instead, we will need to create a script to configure the camera controls.

## Create a New Script

To create a new script, complete the following.
1. Select the Main Camera in the Hierarchy view.
2. In the Inspector, add a New Script Component.
3. Name this script "CameraController". Choose the JavaScript language.
4. In the Project view, organize it so that the CameraController script is in your Scripts folder.
5. Open for editing.

![Camera](https://github.com/junior-devleague/ancient-lands/blob/master/images/main-camera.jpg)

## Problem Solve!

What are we trying to do here?

We want to know how far the player is from the camera.
At every frame, we want to update the camera's position to equal the player's position plus how far the camera was from the player initially. How can we transform this statement into code?

1. Create a variable called **player** that will store a ```GameObject```.
2. Create a private variable called **offset** that will store a ```Vector3```.
3. In the Start() function, obtain the difference in position between the camera's position and the player's position. Store this into the ```offset``` variable. Hint: Research ```transform.position```. If transform.position refers to the camera's position, how do you get the player's position? You should obtain the following:
```JavaScript
offset = transform.position - player.transform.position;
```
4. In the Update() function, update the camera's position to equal the player's position + the initial distance between them. You should obtain the following:
```JavaScript
transform.position = player.transform.position + offset;
```

5. Instead of using the Update() function, we can use the LateUpdate() function to have the camera update its position as late as possible to ensure that it is updating after the player has moved. Change the Update() function to LateUpdate().

At the end, you should obtain the following:
```JavaScript
#pragma strict

var player : GameObject;
private var offset : Vector3;

function Start () {
	offset = transform.position - player.transform.position;

}

function LateUpdate () {
	transform.position = player.transform.position + offset;
}
```
