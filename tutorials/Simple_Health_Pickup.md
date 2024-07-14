
    ## Tutorial 25: Simple Health Pickup

    In this tutorial, we will create a script that allows the player to pick up health items to restore health.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the player.
    - Add several 3D objects to represent health pickups.

    ### Step 2: Creating the Health Pickup Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "HealthPickup" and double-click it to open in your code editor.

    ### Step 3: Writing the Health Pickup Script
    - Inside the HealthPickup script, create the following variables and methods:

    ```csharp
    using UnityEngine;

    public class HealthPickup : MonoBehaviour
    {
        public int healthAmount = 10;

        void OnTriggerEnter(Collider other)
        {
            if (other.CompareTag("Player"))
            {
                PlayerHealth playerHealth = other.GetComponent<PlayerHealth>();
                if (playerHealth != null)
                {
                    playerHealth.Heal(healthAmount);
                    Destroy(gameObject);
                }
            }
        }
    }

    public class PlayerHealth : MonoBehaviour
    {
        public int maxHealth = 100;
        private int currentHealth;

        void Start()
        {
            currentHealth = maxHealth;
        }

        public void Heal(int amount)
        