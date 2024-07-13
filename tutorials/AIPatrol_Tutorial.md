
    ## Tutorial 6: Simple AI Patrol

    In this tutorial, we will create a script that makes an AI character patrol between waypoints.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a cube) to represent the AI character.
    - Add empty GameObjects as waypoints and position them around the scene.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "AIPatrol" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the AIPatrol script, create the following variables:

    ```csharp
    using UnityEngine;

    public class AIPatrol : MonoBehaviour
    {
        public Transform[] waypoints;
        public float speed = 2f;
        private int currentWaypointIndex = 0;

        void Update()
        {
            if (waypoints.Length == 0) return;

            Transform targetWaypoint = waypoints[currentWaypointIndex];
            Vector3 direction = targetWaypoint.position - transform.position;
            transform.Translate(direction.normalized * speed * Time.deltaTime, Space.World);

            if (Vector3.Distance(transform.position, targetWaypoint.position) < 0.1f)
            {
                currentWaypointIndex = (currentWaypointIndex + 1) % waypoints.Length;
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the AI character.
    - Assign the waypoints to the `waypoints` array in the Inspector panel.

    ### Step 5: Testing the Patrol
    - Press the Play button in Unity and observe how the AI character patrols between the waypoints.
    