# SOCollections
Unity tools for adding scriptable object asset files to other scriptable objects as child objects

### Purpose
Scriptable Objects are incredibly useful for storing a variety of persistent data in Unity. Because of this, it's often desireable to have a scriptable hold references to other scriptable objects. However if you try to do this, you might notice that they will lose the reference after restarting the editor. This is because in order for the reference to stick, the scriptable object needs to be 'embedded' in the scriptable object that's referencing it. 

This can be done with a editor method: AssetDatabase.AddObjectToAsset(), but it can be annoying to have to create an editor class just for this, and even if you do it can be a little tricky. The goal of this library is to supply some simple tools to make adding objects to assets easy.

To use SOCollections just copy or clone the files into your project. There are two ways to use the tool:

### Method 1
The simplest way to use this tool is to simply add a SOCollection variable to any ScriptableObject class that needs it, along with the appropriate using directive (using StellarDoor.SOCollection). This will show up like a list in the inspector. 

*image

You can add any object that derives from ScriptableObject to this list by either dragging them onto the list title, or by clicking the '+' button and adding one to the empty element filed that it creates. 

You'll notice that when you do this the scriptable object asset file of the object will move to be a child object of the scriptable object that contains the list. You can verify this by clicking the triangle next to its name to unfold it, if need be.

_What actually happens is that an exact copy of the asset is added to the object, and the original is deleted. While the added object will have all the data of the original, any references to it in other places, e.g. MonoBehaviours that reference it in the scene will lose the reference. Be aware that you'll have to reassign the object in the inspector where needed._ You can do this the same way you would any scriptable object, by dragging it or by using the object picker to locate it.

You can remove the objects by clicking the "X" next to that item. This will delete the child object and create a copy of it in the same folder as the object that was referencing it.

You can also replace an object that's already in the list, either by dragging or by using the object picker. If you do so the replaced item gets copied to a stand alone asset file, while the added item gets copied into the object.

### Method 2

The second method is a little more complex, but can be a powerful way to create and manage groups of scriptable objects of the same type.

*todo


