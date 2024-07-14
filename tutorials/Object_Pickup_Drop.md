
    ## Tutorial 22: Object Pickup and Drop

    In this tutorial, we will create a script that allows the player to pick up and drop objects.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Add several 3D objects to represent items to be picked up.

    ### Step 2: Creating the Pickup Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "Pickup" and double-click it to open in your code editor.

    ### Step 3: Writing the Pickup Script
    - Inside the Pickup script, create the following variables and methods:

    ```csharp
    using UnityEngine;

    public class Pickup : MonoBehaviour
    {
        public Transform player;
        public Transform playerCam;
        public float throwForce = 10;
        private bool hasPlayer = false;
        private bool beingCarried = false;
        private bool touched = false;

        void Update()
        {
            float dist = Vector3.Distance(gameObject.transform.position, player.position);
            if (dist <= 2.5f)
            {
                hasPlayer = true;
            }
            else
            {
                hasPlayer = false;
            }
            if (hasPlayer && Input.GetButtonDown("Use"))
            {
                GetComponent<Rigidbody>().isKinematic = true;
                transform.parent = playerCam;
                beingCarried = true;
            }
            if (beingCarried)
            {
                if (touched)
                {
                    GetComponent<Rigidbody>().isKinematic = false;
                    transform.parent = null;
                    beingCarried = false;
                    touched = false;
                }
                if (Input.GetButtonDown("Use"))
                {
                    GetComponent<Rigidbody>().isKinematic = false;
                    transform.parent = null;
                    beingCarried = false;
                    GetComponent<Rigidbody>().AddForce(playerCam.forward * throwForce);
                }
            }
        }

        void OnTriggerEnter()
        {
            if (beingCarried)
            {
                touched = true;
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the objects to be picked up.
    - Assign the player and player camera Transforms in the Inspector panel.

    ### Step 5: Testing the Pickup System
    - Press the Play button in Unity and use the 'Use' button (default E key) to pick up and drop objects.
    