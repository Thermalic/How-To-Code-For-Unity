
    ## Tutorial 19: Basic Character Controller

    In this tutorial, we will create a script that allows basic character movement and jumping.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the character.

    ### Step 2: Creating the Character Controller Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "CharacterController" and double-click it to open in your code editor.

    ### Step 3: Writing the Character Controller Script
    - Inside the CharacterController script, create the following variables:

    ```csharp
    using UnityEngine;

    public class CharacterController : MonoBehaviour
    {
        public float speed = 5f;
        public float jumpForce = 5f;
        private Rigidbody rb;
        private bool isGrounded;

        void Start()
        {
            rb = GetComponent<Rigidbody>();
        }

        void Update()
        {
            Move();
            Jump();
        }

        void Move()
        {
            float moveHorizontal = Input.GetAxis("Horizontal");
            float moveVertical = Input.GetAxis("Vertical");
            Vector3 movement = new Vector3(moveHorizontal, 0.0f, moveVertical);
            rb.AddForce(movement * speed);
        }

        void Jump()
        {
            if (isGrounded && Input.GetButtonDown("Jump"))
            {
                rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            }
        }

        void OnCollisionStay()
        {
            isGrounded = true;
        }

        void OnCollisionExit()
        {
            isGrounded = false;
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the character.

    ### Step 5: Testing the Character Controller
    - Press the Play button in Unity and use the WASD keys to move and the space bar to jump.
    