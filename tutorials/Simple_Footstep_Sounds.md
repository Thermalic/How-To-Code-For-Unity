
    ## Tutorial 23: Simple Footstep Sounds

    In this tutorial, we will create a script that plays footstep sounds as the player moves.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Import footstep sound clips into the project.

    ### Step 2: Creating the Footstep Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "Footsteps" and double-click it to open in your code editor.

    ### Step 3: Writing the Footstep Script
    - Inside the Footsteps script, create the following variables and methods:

    ```csharp
    using UnityEngine;

    public class Footsteps : MonoBehaviour
    {
        public AudioSource audioSource;
        public AudioClip[] footstepClips;
        private CharacterController controller;

        void Start()
        {
            controller = GetComponent<CharacterController>();
        }

        void Update()
        {
            if (controller.isGrounded && controller.velocity.magnitude > 2f && !audioSource.isPlaying)
            {
                PlayFootstep();
            }
        }

        void PlayFootstep()
        {
            int index = Random.Range(0, footstepClips.Length);
            audioSource.clip = footstepClips[index];
            audioSource.Play();
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the player.
    - Assign the AudioSource and footstep clips in the Inspector panel.

    ### Step 5: Testing the Footstep Sounds
    - Press the Play button in Unity and move the player to hear the footstep sounds.
    