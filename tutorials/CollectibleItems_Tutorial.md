
    ## Tutorial 8: Collectible Items

    In this tutorial, we will create a script that allows a character to collect items.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a sphere) to represent the collectible item.
    - Add a 3D object (e.g., a capsule) to represent the character.

    ### Step 2: Creating the Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "CollectibleItem" and double-click it to open in your code editor.

    ### Step 3: Writing the Script
    - Inside the CollectibleItem script, create the following variables:

    ```csharp
    using UnityEngine;

    public class CollectibleItem : MonoBehaviour
    {
        void OnTriggerEnter(Collider other)
        {
            if (other.CompareTag("Player"))
            {
                // Add collection logic here
                Debug.Log("Item collected");
                Destroy(gameObject);
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to the collectible item.
    - Add a Collider component to the item and set it as a trigger.
    - Tag the character as "Player".

    ### Step 5: Testing the Collectible
    - Press the Play button in Unity and move the character to collect the item.
    