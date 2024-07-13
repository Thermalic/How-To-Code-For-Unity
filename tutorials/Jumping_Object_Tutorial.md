
    ## Tutorial 1: Jumping Object

    In this tutorial, we will create a script that allows an object to jump when the space bar is pressed.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a sphere) to the scene and position it above a plane.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "ObjectJump" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the ObjectJump script, create the following variables:

    ```csharp
    using UnityEngine;

    public class ObjectJump : MonoBehaviour
    {
        public float jumpForce = 5f;
        private Rigidbody rb;

        void Start()
        {
            rb = GetComponent<Rigidbody>();
        }

        void Update()
        {
            if (Input.GetKeyDown(KeyCode.Space))
            {
                rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            }
        }
    }
    ```

    ### Step 4: Adding Rigidbody
    - Add a Rigidbody component to the object.

    ### Step 5: Saving and Assigning the Script
    - Save the script and attach it to the object in the Inspector panel.

    ### Step 6: Testing the Jump
    - Press the Play button in Unity and press the space bar to make the object jump.
    