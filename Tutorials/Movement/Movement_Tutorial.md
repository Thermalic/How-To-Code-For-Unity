
## Tutorial: Object Movement

In this tutorial, we will create a basic script in Unity that enables an object to move towards another object. This is perfect for beginners who want to learn how to code movement behaviors in Unity.

### Step 1: Setting up the Scene
- Open Unity and create a new 3D project.
- Add two 3D objects to the scene. For example, you can use a sphere and a cube.

### Step 2: Creating the Script
- Right-click in the Project panel, then go to Create > C# Script.
- Name the script "ObjectMovement" and double-click it to open in your code editor.

### Step 3: Writing the Script
- Inside the ObjectMovement script, create the following variables:

```csharp
using UnityEngine;

public class ObjectMovement : MonoBehaviour
{
    public Transform target; // The object to move towards

    void Update()
    {
        if (target != null)
        {
            transform.position = Vector3.MoveTowards(transform.position, target.position, Time.deltaTime);
        }
    }
}
```

### Step 4: Assigning the Target
- Save the script and go back to Unity.
- Attach the ObjectMovement script to the object you want to move.
- In the Inspector, assign the target object to the target variable.

### Step 5: Testing the Movement
- Press Play in Unity and observe how the object moves towards the target.
