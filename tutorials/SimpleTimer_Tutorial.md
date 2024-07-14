
    ## Tutorial 10: Simple Timer

    In this tutorial, we will create a script that counts down from a specified time and triggers an event when the time runs out.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a UI Text element to the scene to display the timer.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "SimpleTimer" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the SimpleTimer script, create the following variables:

    ```csharp
    using UnityEngine;
    using UnityEngine.UI;

    public class SimpleTimer : MonoBehaviour
    {
        public float startTime = 60f;
        public Text timerText;
        private float currentTime;

        void Start()
        {
            currentTime = startTime;
        }

        void Update()
        {
            if (currentTime > 0)
            {
                currentTime -= Time.deltaTime;
                timerText.text = currentTime.ToString("F2");
            }
            else
            {
                timerText.text = "Time's up!";
                // Add time's up logic here
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to a GameObject in the scene.
    - Assign the UI Text element to the `timerText` field in the Inspector panel.

    ### Step 5: Testing the Timer
    - Press the Play button in Unity and observe how the timer counts down and displays "Time's up!" when it reaches zero.
    