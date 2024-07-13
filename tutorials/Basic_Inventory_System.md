
    ## Tutorial 11: Basic Inventory System

    In this tutorial, we will create a simple inventory system for collecting items.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add several 3D objects to represent collectible items.
    - Add a 3D object (e.g., a capsule) to represent the character.

    ### Step 2: Creating the Inventory Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "InventorySystem" and double-click it to open in your code editor.

    ### Step 3: Writing the Inventory Script
    - Inside the InventorySystem script, create the following variables:

    ```csharp
    using UnityEngine;
    using System.Collections.Generic;

    public class InventorySystem : MonoBehaviour
    {
        private List<string> inventory = new List<string>();

        void OnTriggerEnter(Collider other)
        {
            if (other.CompareTag("Collectible"))
            {
                inventory.Add(other.gameObject.name);
                Destroy(other.gameObject);
                Debug.Log("Collected: " + other.gameObject.name);
            }
        }

        public void PrintInventory()
        {
            Debug.Log("Inventory: " + string.Join(", ", inventory));
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the character.
    - Tag the collectible items as "Collectible".

    ### Step 5: Testing the Inventory System
    - Press the Play button in Unity and move the character to collect items. Use the `PrintInventory` method to display collected items in the console.
    