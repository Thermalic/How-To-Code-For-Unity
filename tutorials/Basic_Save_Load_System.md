
    ## Tutorial 21: Basic Save and Load System

    In this tutorial, we will create a simple save and load system to save player data.

    ### Step 1: Setting up the Scene
    - Open Unity and create a new 3D project.
    - Add a 3D object (e.g., a cube) to represent the player.

    ### Step 2: Creating the Save System Script
    - Right-click in the Project panel, then go to Create > C# Script.
    - Name the script "SaveSystem" and double-click it to open in your code editor.

    ### Step 3: Writing the Save System Script
    - Inside the SaveSystem script, create the following variables and methods:

    ```csharp
    using UnityEngine;
    using System.IO;
    using System.Runtime.Serialization.Formatters.Binary;

    [System.Serializable]
    public class PlayerData
    {
        public float[] position;
    }

    public class SaveSystem : MonoBehaviour
    {
        public Transform player;

        void Update()
        {
            if (Input.GetKeyDown(KeyCode.S))
            {
                SavePlayer();
            }
            if (Input.GetKeyDown(KeyCode.L))
            {
                LoadPlayer();
            }
        }

        public void SavePlayer()
        {
            BinaryFormatter formatter = new BinaryFormatter();
            string path = Application.persistentDataPath + "/player.fun";
            FileStream stream = new FileStream(path, FileMode.Create);

            PlayerData data = new PlayerData();
            data.position = new float[3];
            data.position[0] = player.position.x;
            data.position[1] = player.position.y;
            data.position[2] = player.position.z;

            formatter.Serialize(stream, data);
            stream.Close();
        }

        public void LoadPlayer()
        {
            string path = Application.persistentDataPath + "/player.fun";
            if (File.Exists(path))
            {
                BinaryFormatter formatter = new BinaryFormatter();
                FileStream stream = new FileStream(path, FileMode.Open);

                PlayerData data = formatter.Deserialize(stream) as PlayerData;
                stream.Close();

                Vector3 position;
                position.x = data.position[0];
                position.y = data.position[1];
                position.z = data.position[2];
                player.position = position;
            }
            else
            {
                Debug.LogError("Save file not found in " + path);
            }
        }
    }
    ```

    ### Step 4: Saving and Assigning the Script
    - Save the script and attach it to an empty GameObject in the scene.
    - Assign the player Transform in the Inspector panel.

    ### Step 5: Testing the Save System
    - Press the Play button in Unity and use the 'S' key to save the player's position and the 'L' key to load the player's position.
    