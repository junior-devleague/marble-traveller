# Collisions

## Introduction
We want to 'pick up' our collectible objects. What does this actually mean? When our player sphere touches the pick up object, we want our pick up object to disappear. This means that when we collide any object, we need to check what this object is. If it is a pickup object, we will deactivate this object and visibly remove it from our scene.

## Detecting Collisions

To detect and check what object we are colliding with, complete the following.

1. Open up the Player Controller script for your player sphere.
2. Outside of your Start and FixedUpdate functions, we are going to create a new function. Research ```OnTriggerEnter```. This function will give us a reference to the object that we are colliding with when we move around the scene. Thus, we can access the gameObject from this information using other.gameObject. Create a function OnTriggerEnter that will compare the tag of the gameObject that was collided to "Pickup". If the tag is "Pickup", set the gameObject's Active value to false.

Your code should look something like this:
```JavaScript
function OnTriggerEnter (other : Collider) {
  if (____if the tag is "Pickup"______) {
    _____set the game object active value to false_____
  }
}
```

Hint: Research, OnTriggerEnter, CompareTag, and SetActive!

3. We now need to add the "Pickup" tag to our pickup objects. In the Project View, select your Prefab object. In the Inspector, click on the Tag dropdown at the top and select 'Add Tag'.

![Add Tag](https://github.com/junior-devleague/ancient-lands/blob/master/images/add-tag.jpg)

4. Click on the + icon and call this tag "Pickup". This needs to be the same tag that you specified in your code!

![Add Tag P2](https://github.com/junior-devleague/ancient-lands/blob/master/images/add-tag-2.jpg)

5. In the Inspector view, click on the Tag dropdown and select the newly created Pickup tag.

6. Click on the Prefab in your Project View. Look at the Box Collider component in the Inspector. We want this to be a trigger that will respond to our OnTriggerEnter code. In Box Collider, check the box, "Is Trigger".

![Trigger](https://github.com/junior-devleague/ancient-lands/blob/master/images/is-trigger.jpg)

7. Unity will cache (store) information about static objects so it doesn't need to recalculate the static object's position every frame! We can move or rotate **dynamic** colliders and Unity will not recache this information. To do so, we will need a Rigidbody. Right now, our cubes are considered static objects because we do not have a Rigidbody component. Add a Rigidbody component to the Prefab.

8. In the Rigidbody Component, check the box "Is Kinematic". A Kinematics Rigidbody will not respond to Physics forces. Thus, it will not be pulled down by gravity but can still be moved by the transformations we specify.

![Kinematic](https://github.com/junior-devleague/ancient-lands/blob/master/images/is-kinematic.jpg)

9. Run the game! Does the player object pick them up as expected?

## Stretch Goals
1. Make the object get bigger onTriggerEnter!
