# Creating Scripts

## Introduction
How do we move our player? We need to take user input and apply it as forces to our object. Since we need to add this functionality, it's time to create a script!

## JavaScript vs. UnityScript
In Unity, developers have the choice of scripting in JavaScript or C#. We will be using JavaScript. However, Unity uses its own similar to JavaScript language, UnityScript. You will begin to see the differences between the two.  

In general, UnityScript:
* Requires semi colons
* Requires data type after declaration of variable name (e.g. var text : String = "Hello!")

## Scripts folder

1. Create a folder that will store all of your scripts. In your Project View, Create -> New Folder. Name this folder "Scripts".
2. Select the Player Object.
3. Add a New Script component in the Inspector as shown below.

![New Script](https://github.com/junior-devleague/ancient-lands/blob/master/images/new-script.jpg)

4. Name the New Script, "PlayerController".
5. Select JavaScript as the language.
6. Drag this new script into the Scripts folder in the Hierarchy view.
7. Double click on this script to open it. This will take you to the MonoDevelop Editor!
8. You start with a function Start() and a function Update(). When dealing with physics, we want Unity to run our script dealing with physics on a FixedUpdate() function.

*Why? The function Update() will call the function every frame and if one frame takes longer to process, the interval will be inconsistent. Meanwhile, FixedUpdate() will call the function every physics step and the interval is consistent. This is used for updates that will adjust physics (Rigidbody).*

9. Create a function called FixedUpdate().
10. Think about what we want to do here.

*We want to retrieve user input (arrow keys) and apply them as forces to our object. Let's start with the input.*

11. Type in 'Input' in the editor. Select the word and press CMD + ' on your keyboard. This will bring up all of the relevant links for UnityScript. Read the descriptions and look for what we might want. In this case, we need Input.GetAxis. Store the Horizontal and Vertical axis information in variables moveVertical and moveHorizontal. You should have the following:
```JavaScript
var moveVertical : float = Input.GetAxis("Vertical");
var moveHorizontal : float = Input.GetAxis("Horizontal");
```

12. Now, we want to apply these inputs as forces to our object. How do we add a force to our Rigidbody? First, let's obtain our Rigidbody component by storing it in a variable. Declare a variable rb at the top of our editor that will store a Rigidbody. You should have the following:
```JavaScript
var rb : Rigidbody;
```

13. Let's obtain the Rigidbody component that is attached to our player. In the Start() function, get the component Rigidbody and store it in our variable rb. You should have the following:
```JavaScript
rb = GetComponent.<Rigidbody>();
```
14. It's time to apply our input as forces to this Rigidbody. Type in 'AddForce' in the editor. Select the word and press CMD + ' on your keyboard. This will bring up all of the relevant links for UnityScript. Read the descriptions and look for what we might want. In this case, we need AddForce(Vector3). Let's create a Vector3. A Vector3 will need x, y, and z values. Since our player will not be going upwards, our y value is 0. Where will our x and z values come from? Store a Vector3 in a variable called movement. You should have the following:
```JavaScript
var movement : Vector3 = Vector3(moveHorizontal, 0, moveVertical);
```

*What is a Vector3? A Vector 3 holds (x,y,z) coordinates that are important for moving and rotating in 3D space.*

15. We have our Vector3, how do we apply this? Add this force to the Rigidbody component. You should have the following:
```JavaScript
rb.AddForce(movement);
```
16. Save what you have and go back to the Unity Main Editor window. Press the Play button in the Toolbar and check for any errors.

17. Upon pressing the arrow keys, you should have very, very slow movement. We need the ball to go faster for our game! Go back to the script.

18. In your script, create a variable speed with float values. Nothing should be assigned to this variable just yet. This variable should be at the top of your script. You should have the following:
```JavaScript
var speed : float;
```

19. What do we need the speed for? Our speed needs to be multiplied with our movement so that our ball speeds up as we hold our arrow keys down. You should have the following:
```JavaScript
rb.AddForce(movement*speed);
```

20. In Unity, public variables can be changed in the editor. This allows us to test different values and watch how our game changes quickly. Go back to the Unity main editor and look at your inspector for the Player Object. Under the Player Control script, the variable speed can take in numbers. Test out a few numbers for your speed and run the game.

At the end you should obtain the following:
```JavaScript
#pragma strict

var rb: Rigidbody;
var speed: int;

function Start () {
	rb = GetComponent.<Rigidbody>();
}

function FixedUpdate () {
	var moveVertical : float = Input.GetAxis("Vertical");
	var moveHorizontal : float = Input.GetAxis("Horizontal");

	var movement : Vector3 = Vector3(moveHorizontal, 0	, moveVertical);
	rb.AddForce(movement*speed);

}
``` 
