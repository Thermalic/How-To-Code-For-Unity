
## Tutorial: Object Rotation

In this tutorial, we will create a script that allows an object to rotate continuously.

### Step 1: Setting up the Scene
- Open Unity and create a new 3D project.
- Add a 3D object (e.g., a cube) to the scene.

### Step 2: Creating the Script
- Right-click in the Project panel, then go to Create > C# Script.
- Name the script "ObjectRotation" and double-click it to open in your code editor.

### Step 3: Writing the Script
- Inside the ObjectRotation script, create the following variables:

```csharp
using UnityEngine;

public class ObjectRotation : MonoBehaviour
{
    public Vector3 rotationSpeed = new Vector3(0, 100, 0);

    void Update()
    {
        transform.Rotate(rotationSpeed * Time.deltaTime);
    }
}
```

### Step 4: Saving and Assigning the Script
- Save the script and attach it to the object.

### Step 5: Testing the Rotation
- Press the Play button in Unity and observe how the object rotates.
