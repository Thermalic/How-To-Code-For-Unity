
    ## Tutorial 14: Day-Night Cycle

    In this tutorial, we will create a simple day-night cycle using a directional light.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a Directional Light to the scene.

    ### Step 2: Creating the Day-Night Cycle Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "DayNightCycle" and double-click it to open in your code editor.

    ### Step 3: Writing the Day-Night Cycle Script
    - Inside the DayNightCycle script, create the following variables:

    ```csharp
    using UnityEngine;

    public class DayNightCycle : MonoBehaviour
    {
        public float dayLength = 120f; // Length of a day in seconds
        private Light directionalLight;
        private float time;

        void Start()
        {
            directionalLight = GetComponent<Light>();
        }

        void Update()
        {
            time += Time.deltaTime;
            float dayProgress = time / dayLength;
            directionalLight.transform.rotation = Quaternion.Euler(dayProgress * 360f - 90f, 170f, 0f);
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the directional light.

    ### Step 5: Testing the Day-Night Cycle
    - Press the Play button in Unity and observe the day-night cycle.
    