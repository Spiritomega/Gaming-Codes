# **Unity Object Pooler Pro**

Unity Object Pooler Pro is an efficient and scalable object pooling system designed for Unity projects. It optimizes game performance by reusing objects instead of creating and destroying them repeatedly. Perfect for games with high object spawning rates, like shooters, platformers, or particle systems. 🚀🎮

---

### **Features**
1. **Dynamic Object Pooling**: Create pools of reusable objects for efficient memory and performance management.
2. **Customizable Pools**: Define multiple pools with unique tags, prefabs, and sizes directly in the Unity Inspector.
3. **Scalable Design**: Automatically expands pools when objects run out, ensuring smooth gameplay.
4. **Reusability**: Spawn inactive objects from the pool and reset them for seamless reuse.
5. **Ease of Integration**: Drop-in ready with minimal setup.

---

### **How It Works**
1. **Define Pools**: In the Unity Inspector, specify the prefab, size, and tag for each pool.
2. **Initialize Pools**: The system preloads objects for each pool on startup, deactivating them to save resources.
3. **Spawn Objects**: Use the `SpawnFromPool()` method to retrieve objects, position them, and activate them for gameplay.
4. **Reuse Objects**: Deactivated objects return to the pool for future use, reducing memory allocation and garbage collection.

---

### **Code Overview**
- **`Pool` Class**: Holds the tag, prefab, and size for each object pool.
- **`ObjectPooler` Class**: Manages pool creation, object spawning, and dynamic resizing.
- **`SpawnFromPool()` Method**: Retrieves an object from the pool, initializes its position and rotation, and activates it for use.

---

### **Setup Instructions**
1. Import the script into your Unity project.
2. Attach the `ObjectPooler` script to an empty GameObject.
3. In the Inspector, define the pools by adding:
   - **Tag**: Unique identifier for the pool.
   - **Prefab**: GameObject to pool.
   - **Size**: Initial number of objects in the pool.
4. Call `ObjectPooler.opInstance.SpawnFromPool(tag, position, rotation)` to spawn objects.

---

### **Example Usage**
```csharp
void SpawnEnemy()
{
    Vector2 spawnPosition = new Vector2(0, 0);
    Quaternion spawnRotation = Quaternion.identity;
    GameObject enemy = ObjectPooler.opInstance.SpawnFromPool("Enemy", spawnPosition, spawnRotation);
    if (enemy != null)
    {
        // Additional logic for the spawned enemy
    }
}
```

---

### **Requirements**
- Unity 2020.3 or later.
- Prefabs for each object you want to pool.

---

### **Who Is It For?**
- Developers building games with frequent spawning (e.g., bullets, enemies, effects).
- Projects that need to optimize performance by reducing instantiation overhead.
- Teams looking for a reusable and scalable pooling solution.

---

### **Future Upgrades**
- Add a pooling UI system for managing pools in real-time.
- Implement object recycling logic to limit pool size dynamically.
- Support for pooling audio sources or other Unity components.

---

Ready to take your Unity project to the next level? Optimize your game's performance with **Unity Object Pooler Pro** today! 🎯✨
