
    ## Tutorial 13: Simple Minimap

    In this tutorial, we will create a simple minimap that shows the player's position in the scene.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Create a UI Canvas for the minimap and add a Raw Image to display the minimap.

    ### Step 2: Creating the Minimap Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "Minimap" and double-click it to open in your code editor.

    ### Step 3: Writing the Minimap Script
    - Inside the Minimap script, create the following variables:

    ```csharp
    using UnityEngine;

    public class Minimap : MonoBehaviour
    {
        public Transform player;
        public Camera minimapCamera;

        void LateUpdate()
        {
            Vector3 newPosition = player.position;
            newPosition.y = minimapCamera.transform.position.y;
            minimapCamera.transform.position = newPosition;
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the minimap camera.
    - Assign the player and minimap camera in the Inspector panel.

    ### Step 5: Testing the Minimap
    - Press the Play button in Unity and move the player to see the minimap update.
    