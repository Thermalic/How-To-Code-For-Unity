
    ## Tutorial 17: Teleportation System

    In this tutorial, we will create a script that teleports the player to different locations.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Create empty GameObjects to represent the teleportation points.

    ### Step 2: Creating the Teleportation Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "TeleportationSystem" and double-click it to open in your code editor.

    ### Step 3: Writing the Teleportation Script
    - Inside the TeleportationSystem script, create the following variables:

    ```csharp
    using UnityEngine;

    public class TeleportationSystem : MonoBehaviour
    {
        public Transform[] teleportPoints;

        void Update()
        {
            if (Input.GetKeyDown(KeyCode.Alpha1))
            {
                TeleportTo(0);
            }
            else if (Input.GetKeyDown(KeyCode.Alpha2))
            {
                TeleportTo(1);
            }
            else if (Input.GetKeyDown(KeyCode.Alpha3))
            {
                TeleportTo(2);
            }
        }

        void TeleportTo(int index)
        {
            if (index < teleportPoints.Length)
            {
                transform.position = teleportPoints[index].position;
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the player.
    - Assign the teleport points in the Inspector panel.

    ### Step 5: Testing the Teleportation System
    - Press the Play button in Unity and use keys 1, 2, and 3 to teleport the player to different points.
    