- **Classes, Objects & Properties**
    Question: you do class like **class House{}**, and objects will be **House blueHouse = new House**, and the properties will be **"wall", "roof", "rooms"**?
    Answer: Yes!
    
    ```csharp
    // This is the CLASS (Blueprint)
    class House {
        public string wall;   // Property
        public string roof;   // Property
        public int rooms;     // Property
    
        public void Describe() {
            Console.WriteLine($"This house has {wall} walls, a {roof} roof, and {rooms} rooms.");
        }
    }
    
    // This is where we create OBJECTS based on the CLASS
    class Program {
        static void Main() {
            House blueHouse = new House();  // Creating an object
            blueHouse.wall = "blue";        // Assigning property values
            blueHouse.roof = "gray";
            blueHouse.rooms = 3;
    
            House redHouse = new House();  // Another object
            redHouse.wall = "red";
            redHouse.roof = "black";
            redHouse.rooms = 5;
    
            blueHouse.Describe();  // Output: This house has blue walls, a gray roof, and 3 rooms.
            redHouse.Describe();   // Output: This house has red walls, a black roof, and 5 rooms.
        }
    }
    ```
    
    - **`class House {}`** → The **blueprint** of a house
    - **`House blueHouse = new House();`** → The **object** (actual house)
    - **Properties (`wall`, `roof`, `rooms`)** → The **features** of each house
    
    <aside>
    Question: it looks like you **just instantiated a class when it comes to declaring an object**. is that how it works? what does it mean when you instantiate?
    Answer: 
    Yes! When you **declare an object**, you're actually **instantiating** a class.
    </aside>
    
    ### **📌 What Does "Instantiate" Mean?**
    **Instantiation** means **creating an actual object** (a real thing) from a class (a blueprint).
    Think of a class as a **mold** for making a cup.
    
    - **The class** (`Cup`) = The mold
    - **Instantiation** = Pouring clay into the mold to create an actual cup
    - **The object** (`myCup`) = The real cup you can hold
    
    **In C#, this is how we instantiate a class:**
    
    ```csharp
    House blueHouse = new House();
    ```
    Here's what's happening in that line:
    
    1️⃣ `House` → The **class** (blueprint)
    2️⃣ `blueHouse` → The **object** (actual thing created)
    3️⃣ `new House();` → This is the **instantiation** part—it creates a new object in memory
    
    ### **🔍 Why Do We Need Instantiation?**
    Without instantiation, a class is just an idea—it **doesn’t exist in memory** yet. You need to instantiate it so the computer knows, **"Okay, this is an actual object I need to store and work with!"** Example:
    
    ```csharp
    class Dog {
        public string name;
    }
    
    // Instantiating the Dog class (creating an object)
    Dog myDog = new Dog();
    myDog.name = "Buddy";  // Now it has a real name!
    Console.WriteLine(myDog.name);  // Output: Buddy
    ```
    
    Without `new Dog();`, the object **wouldn’t exist in memory**, so you couldn’t set or use its properties.
    <aside>
    ### **🔥 Quick Recap**
    ✅ **Declaring an object = Instantiating a class**
    ✅ Instantiation is just **bringing a class to life in memory**
    ✅ Without instantiation, a class is just a concept, not a real thing
    </aside>
