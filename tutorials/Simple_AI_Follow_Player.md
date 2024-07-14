
    ## Tutorial 24: Simple AI Follow Player

    In this tutorial, we will create a script that makes an AI character follow the player.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Add a 3D object (e.g., a cube) to represent the AI character.

    ### Step 2: Creating the AI Follow Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "AIFollow" and double-click it to open in your code editor.

    ### Step 3: Writing the AI Follow Script
    - Inside the AIFollow script, create the following variables and methods:

    ```csharp
    using UnityEngine;

    public class AIFollow : MonoBehaviour
    {
        public Transform player;
        public float speed = 5f;

        void Update()
        {
            float step = speed * Time.deltaTime;
            transform.position = Vector3.MoveTowards(transform.position, player.position, step);
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the AI character.
    - Assign the player Transform in the Inspector panel.

    ### Step 5: Testing the AI Follow
    - Press the Play button in Unity and move the player to see the AI character follow the player.
    