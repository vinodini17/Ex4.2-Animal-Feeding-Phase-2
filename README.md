# Ex4.2-Animal-Feeding-Phase-2

## Aim :

To develop a animal feeding game-Phase-2 using unity.

## Algorithm :

### Step 1 :

In the Hierarchy, create an Empty object called “SpawnManager”

### Step 2 :

Create a new script called “SpawnManager”, drag the script and attach it to the Spawn Manager in the hierarchy , and open it

### Step 3 :

Declare new public GameObject[ ] animalPrefabs;

### Step 4 :

In the inspector assign the size as 3 , for each element drag the animals from prefabs folder into the array

### Step 5 :

Double-click on one of the animal prefabs, then Add Component > Box Collider

### Step 6 :

Check the “Is Trigger” checkbox

### Step 7 :

Add a RigidBody component to the (banana)projectile and uncheck “use gravity”.

### Step 8 :

Create a new DetectCollisions.cs script, then drag the scripts and add it to each animal prefab and banana, then open it and check it.

### Step 9 :

For all the animal prefabs and food in th inspector (below the layer ) drop down the override option and choose apply all.



## PROGRAM :

### DEVELOPED BY : Vinodini R
### REG NO : 212223040244

## SPAWN MANAGER :

```
 using UnityEngine;
using System.Collections;
using System.Collections.Generic;

public class SpawnManager : MonoBehaviour
{

    public GameObject[] animalPrefabs;
    private float spamRangeX=5;
    private float spamPosZ=2;
    private float startDelay=2;
    private float spamInterval=1.5f;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        InvokeRepeating("SpawnRandomAnimal",startDelay, spamInterval);
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    void SpawnRandomAnimal()
    {
        int animalIndex = Random.Range(0, animalPrefabs.Length);
        Vector3 spamPos = new Vector3(Random.Range(-spamRangeX,spamRangeX),0 ,spamPosZ);
        Instantiate(animalPrefabs[animalIndex],spamPos, animalPrefabs[animalIndex].transform.rotation);
    }
}
      
```
## Collision Script
```
using UnityEngine;
using System.Collections.Generic;
using System.Collections;

public class DetectCollider : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    private void OnTriggerEnter(Collider other)
    {
        Destroy(gameObject);
        Destroy(other.gameObject);
    }
}


```
## OUTPUT :

![image](https://github.com/user-attachments/assets/60839871-9278-4b06-894b-acc474054fe1)

## RESULT :

Animal feeding game-Phase-2 using unity is developed successfully.
