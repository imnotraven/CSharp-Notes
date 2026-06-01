### **What is Encapsulation?**

Encapsulation is like putting your **important stuff inside a locked box** and **only giving access in a controlled way**.

**In C#, encapsulation means:**

✅ Keeping data **hidden** inside a class.

✅ Allowing **controlled access** through **methods or properties**.

✅ **Protecting** data from accidental changes.

---

### **Why is Encapsulation Important?**

Encapsulation helps in:

✔ **Data Security:** Prevents outside code from changing important values directly.

✔ **Data Integrity:** Ensures data is **correct** and **consistent**.

✔ **Code Maintainability:** Makes the code **cleaner** and **easier to manage**.

---

### **How Do We Achieve Encapsulation?**

We achieve encapsulation in **three** steps:

**1️⃣ Use `private` fields** (Hide the Data)

**2️⃣ Use `public` properties** (Controlled Access)

**3️⃣ Use `get` and `set` methods** (To Control Read/Write)

---

### **Example (Without Encapsulation) - BAD CODE**

🚨 **Problem:** Anyone can directly change the data, even incorrectly!

```csharp
class BankAccount {
    public double balance;  // ❌ Anyone can change this freely
}

class Program {
    static void Main() {
        BankAccount myAccount = new BankAccount();
        myAccount.balance = -1000;  // ❌ WRONG! Negative balance is unrealistic.
        Console.WriteLine(myAccount.balance);
    }
}
```

😨 **This is bad** because anyone can **change `balance` directly**, even to **invalid values**.

---

### **Example (With Encapsulation) - GOOD CODE**

✅ **Solution:** Use `private` fields and `public` properties with **get/set**

```csharp
class BankAccount {
    private double balance;  // ✅ Hiding the data (Encapsulation)

    // ✅ Controlled access with a property
    public double Balance {
        get { return balance; }  // ✅ Read value
        set {
            if (value >= 0)  // ✅ Only allow valid values
                balance = value;
            else
                Console.WriteLine("Balance cannot be negative!");
        }
    }
}

class Program {
    static void Main() {
        BankAccount myAccount = new BankAccount();
        myAccount.Balance = 500;  // ✅ Valid
        myAccount.Balance = -1000;  // ❌ Invalid! Error message shown.
        Console.WriteLine(myAccount.Balance);  // ✅ Output: 500
    }
}
```

✔ Now, **`balance` is protected** (cannot be changed directly).

✔ **Only valid values** are allowed (no negatives).

✔ **Code is safer** and **maintainable**.

---

### **Additional Information**

**🔹 1. Read-Only and Write-Only Properties**

If you want a property that can **only be read but not modified**, use **`get` only**:

```csharp
class Person {
    private string name = "Alice";

    public string Name {  // ✅ Read-Only Property
        get { return name; }
    }
}
```

**Usage:**

```csharp
Person p = new Person();
Console.WriteLine(p.Name);  // ✅ Allowed
p.Name = "Bob";  // ❌ Error! Cannot modify.
```

If you want a property that can **only be modified but not read**, use **`set` only**:

```csharp
class Secret {
    private string password;

    public string Password {
        set { password = value; }  // ✅ Write-Only Property
    }
}
```

**Usage:**

```csharp
Secret s = new Secret();
s.Password = "MySecret123";  // ✅ Allowed
Console.WriteLine(s.Password);  // ❌ Error! Cannot read.
```

---

<aside>
💡

### **TL;DR (Summary)**

1️⃣ **Encapsulation = Protecting data** by hiding fields and controlling access.

2️⃣ **Use `private` fields** so data cannot be changed directly.

3️⃣ **Use `public` properties with `get/set`** for controlled access.

4️⃣ **Improves security, prevents errors, and makes the code maintainable.**

</aside>
