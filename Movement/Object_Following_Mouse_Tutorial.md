
## Tutorial: Object Following Mouse

In this tutorial, we will create a script that makes an object follow the mouse cursor on the screen.

### Step 1: Setting up the Scene
- Open Unity and create a new 3D project.
- Add a 3D object (e.g., a cube) to the scene.

### Step 2: Creating the Script
- Right-click in the Project panel, then go to Create > C# Script.
- Name the script "MouseFollower" and double-click it to open in your code editor.

### Step 3: Writing the Script
- Inside the MouseFollower script, create the following variables:

```csharp
using UnityEngine;

public class MouseFollower : MonoBehaviour
{
    void Update()
    {
        Vector3 mousePosition = Input.mousePosition;
        mousePosition.z = Camera.main.nearClipPlane;
        transform.position = Camera.main.ScreenToWorldPoint(mousePosition);


    }
}
```

### Step 4: Saving and Assigning the Script
- Save the script and attach it to the object in the Inspector panel.

### Step 5: Testing the Script
- Press the Play button in Unity and observe how the object follows the mouse cursor.
