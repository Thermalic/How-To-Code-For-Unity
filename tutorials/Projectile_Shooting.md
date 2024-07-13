
    ## Tutorial 18: Projectile Shooting

    In this tutorial, we will create a script that allows the player to shoot projectiles.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Create a projectile prefab (e.g., a sphere).

    ### Step 2: Creating the Shooting Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "ProjectileShooting" and double-click it to open in your code editor.

    ### Step 3: Writing the Shooting Script
    - Inside the ProjectileShooting script, create the following variables:

    ```csharp
    using UnityEngine;

    public class ProjectileShooting : MonoBehaviour
    {
        public GameObject projectilePrefab;
        public Transform shootingPoint;
        public float projectileSpeed = 10f;

        void Update()
        {
            if (Input.GetButtonDown("Fire1"))
            {
                ShootProjectile();
            }
        }

        void ShootProjectile()
        {
            GameObject projectile = Instantiate(projectilePrefab, shootingPoint.position, shootingPoint.rotation);
            Rigidbody rb = projectile.GetComponent<Rigidbody>();
            rb.velocity = shootingPoint.forward * projectileSpeed;
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the player.
    - Assign the projectile prefab and shooting point in the Inspector panel.

    ### Step 5: Testing the Shooting System
    - Press the Play button in Unity and use the fire button (left mouse button) to shoot projectiles.
    