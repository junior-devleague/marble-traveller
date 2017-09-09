# Prefabs

## Introduction
A **Prefab** is an asset that contains a template or blueprint of a Game Object or Game Object family. We will be creating a Prefab from an existing Game Object. Once created, we can use this Prefab in any scene! Let's make our collectible item a Prefab. Then, we can make multiple collectible objects. If we ever need to change how our collectibles act or look, we only have to change one!  

## Creating Prefabs

To create a prefab, complete the following.

1. Create a new folder to hold our Prefabs. Make sure nothing is selected in the Project View. Then, select Create -> Folder.
2. Rename this folder 'Prefabs'.
3. Drag the Pickup object from the Hierarchy menu to the Prefabs Folder in your Project view.
4. Create an Empty Object from the GameObject Menu -> Create Empty. In the Hierarchy, rename this GameObject to 'Pickups'. We will store all of our pickups in this.

![Empty Object](https://github.com/junior-devleague/ancient-lands/blob/master/images/empty-object.jpg)

5. In the Hierarchy view, drag your 'Pickup' Object to the 'Pickups' Empty Object we just created.
6. Click on the top cone in the Gizmo located at the top right corner of your Scene view. Make sure you are in Global mode as indicated in the arrows below.

![Top View](https://github.com/junior-devleague/ancient-lands/blob/master/images/global-top-view.jpg)

7. Click on your Pickup object. Duplicate this object (CMD + D), and place 10 Pickup objects in your scene.
![Duplicate Object](https://github.com/junior-devleague/ancient-lands/blob/master/images/duplicate-objects.jpg)


8. Run the game! All of your Pickup objects should be rotating!
