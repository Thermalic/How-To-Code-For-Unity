
## Tutorial: Color Changing Object

In this tutorial, we will create a script that changes the color of an object over time.

### Step 1: Setting up the Scene
- Open Unity and create a new 3D project.
- Add a 3D object (e.g., a sphere) to the scene.

### Step 2: Creating the Script
- Right-click in the Project panel, then go to Create > C# Script.
- Name the script "ColorChanger" and double-click it to open in your code editor.

### Step 3: Writing the Script
- Inside the ColorChanger script, create the following variables:

```csharp
using UnityEngine;

public class ColorChanger : MonoBehaviour
{
    public float colorChangeSpeed = 1f;
    private Renderer renderer;

    void Start()
    {
        renderer = GetComponent<Renderer>();
    }

    void Update()
    {
        float t = Mathf.PingPong(Time.time * colorChangeSpeed, 1);
        renderer.material.color = Color.Lerp(Color.red, Color.blue, t);
    }
}
```

### Step 4: Saving and Assigning the Script
- Save the script and attach it to the object in the Inspector panel.

### Step 5: Testing the Color Change
- Press the Play button in Unity and observe how the object changes color over time.
