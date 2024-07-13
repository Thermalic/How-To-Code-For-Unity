
    ## Tutorial 15: Enemy Spawner

    In this tutorial, we will create a script that spawns enemies at regular intervals.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a cube) to represent the enemy.

    ### Step 2: Creating the Enemy Spawner Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "EnemySpawner" and double-click it to open in your code editor.

    ### Step 3: Writing the Enemy Spawner Script
    - Inside the EnemySpawner script, create the following variables:

    ```csharp
    using UnityEngine;

    public class EnemySpawner : MonoBehaviour
    {
        public GameObject enemyPrefab;
        public Transform[] spawnPoints;
        public float spawnInterval = 5f;
        private float spawnTimer;

        void Update()
        {
            spawnTimer += Time.deltaTime;
            if (spawnTimer >= spawnInterval)
            {
                SpawnEnemy();
                spawnTimer = 0f;
            }
        }

        void SpawnEnemy()
        {
            int spawnIndex = Random.Range(0, spawnPoints.Length);
            Instantiate(enemyPrefab, spawnPoints[spawnIndex].position, spawnPoints[spawnIndex].rotation);
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to an empty GameObject in the scene.
    - Assign the enemy prefab and spawn points in the Inspector panel.

    ### Step 5: Testing the Enemy Spawner
    - Press the Play button in Unity and observe the enemies spawning at regular intervals.
    