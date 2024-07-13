
    ## Tutorial 20: Simple Pause Menu

    In this tutorial, we will create a simple pause menu that can pause and resume the game.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a UI Canvas and create a UI Panel for the pause menu.
    - Add UI Buttons for "Resume" and "Quit".

    ### Step 2: Creating the Pause Menu Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "PauseMenu" and double-click it to open in your code editor.

    ### Step 3: Writing the Pause Menu Script
    - Inside the PauseMenu script, create the following variables:

    ```csharp
    using UnityEngine;

    public class PauseMenu : MonoBehaviour
    {
        public GameObject pauseMenuUI;
        private bool isPaused = false;

        void Update()
        {
            if (Input.GetKeyDown(KeyCode.Escape))
            {
                if (isPaused)
                {
                    Resume();
                }
                else
                {
                    Pause();
                }
            }
        }

        public void Resume()
        {
            pauseMenuUI.SetActive(false);
            Time.timeScale = 1f;
            isPaused = false;
        }

        void Pause()
        {
            pauseMenuUI.SetActive(true);
            Time.timeScale = 0f;
            isPaused = true;
        }

        public void QuitGame()
        {
            Application.Quit();
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to a GameObject in the scene.
    - Assign the UI Panel to the `pauseMenuUI` field in the Inspector panel.

    ### Step 5: Testing the Pause Menu
    - Press the Play button in Unity and use the Escape key to pause and resume the game. Use the "Resume" button to resume and the "Quit" button to quit the game.
    