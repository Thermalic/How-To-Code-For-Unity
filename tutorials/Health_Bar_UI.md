
    ## Tutorial 12: Health Bar UI

    In this tutorial, we will create a health bar UI that displays the character's health.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a capsule) to represent the character.
    - Add a UI Canvas and create a UI Slider to represent the health bar.

    ### Step 2: Creating the Health Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "HealthBar" and double-click it to open in your code editor.

    ### Step 3: Writing the Health Script
    - Inside the HealthBar script, create the following variables:

    ```csharp
    using UnityEngine;
    using UnityEngine.UI;

    public class HealthBar : MonoBehaviour
    {
        public Slider healthSlider;
        public int maxHealth = 100;
        private int currentHealth;

        void Start()
        {
            currentHealth = maxHealth;
            healthSlider.maxValue = maxHealth;
            healthSlider.value = currentHealth;
        }

        public void TakeDamage(int damage)
        {
            currentHealth -= damage;
            healthSlider.value = currentHealth;
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
    - Assign the UI Slider to the `healthSlider` field in the Inspector panel.

    ### Step 5: Testing the Health Bar
    - Press the Play button in Unity and call the `TakeDamage` method to see the health bar update.
    