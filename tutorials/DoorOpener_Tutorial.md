
    ## Tutorial 9: Door Opening System

    In this tutorial, we will create a script that allows a character to open a door.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a door model) to the scene.
    - Add a 3D object (e.g., a capsule) to represent the character.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "DoorOpener" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the DoorOpener script, create the following variables:

    ```csharp
    using UnityEngine;

    public class DoorOpener : MonoBehaviour
    {
        public Transform door;
        public Vector3 openPosition;
        public float openSpeed = 2f;

        private bool isOpen = false;

        void OnTriggerEnter(Collider other)
        {
            if (other.CompareTag("Player"))
            {
                isOpen = true;
            }
        }

        void Update()
        {
            if (isOpen)
            {
                door.position = Vector3.Lerp(door.position, openPosition, Time.deltaTime * openSpeed);
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the door.
    - Add a Collider component to the door and set it as a trigger.
    - Tag the character as "Player".

    ### Step 5: Testing the Door Opener
    - Press the Play button in Unity and move the character to open the door.
    