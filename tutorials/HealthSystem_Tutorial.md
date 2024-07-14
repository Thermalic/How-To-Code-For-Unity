
    ## Tutorial 7: Health System

    In this tutorial, we will create a simple health system for a character.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the character.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "HealthSystem" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the HealthSystem script, create the following variables:

    ```csharp
    using UnityEngine;

    public class HealthSystem : MonoBehaviour
    {
        public int maxHealth = 100;
        private int currentHealth;

        void Start()
        {
            currentHealth = maxHealth;
        }

        public void TakeDamage(int damage)
        {
            currentHealth -= damage;
            if (currentHealth <= 0)
            {
                Die();
            }
        }

        private void Die()
        {
            // Add death logic here
            Debug.Log("Character died");
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the character.

    ### Step 5: Testing the Health System
    - Call the `TakeDamage` method from another script or through the Inspector to test the health system.
    