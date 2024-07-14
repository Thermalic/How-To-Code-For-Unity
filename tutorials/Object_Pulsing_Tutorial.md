
    ## Tutorial 5: Object Pulsing

    In this tutorial, we will create a script that makes an object pulse (scale up and down repeatedly).

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a cube) to the scene.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "ObjectPulsing" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the ObjectPulsing script, create the following variables:

    ```csharp
    using UnityEngine;

    public class ObjectPulsing : MonoBehaviour
    {
        public float pulseSpeed = 1f;
        public float maxScale = 1.5f;
        public float minScale = 0.5f;

        void Update()
        {
            float scale = minScale + Mathf.PingPong(Time.time * pulseSpeed, maxScale - minScale);
            transform.localScale = new Vector3(scale, scale, scale);
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the object in the Inspector panel.

    ### Step 5: Testing the Pulsing
    - Press the Play button in Unity and observe how the object pulses.
    