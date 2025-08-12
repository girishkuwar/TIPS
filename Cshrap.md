
# 🧾 C# Cheat Sheet
📦 Basic Program Structure
```csharp
Copy
Edit
using System;

class Program
{
    static void Main(string[] args)
    {
        // Code goes here
    }
}
```
🔤 Data Types
| Type | Example |
|--|--|
| int| x= 10; |
|float|float y = 5.5f;|
|double|	double z = 3.14;
|char|	char c = 'A';
|string|	string name = "Joe";
|bool|	bool isOn = true;

🔁 Control Structures
If / Else
```csharp
if (x > 0)
{
    Console.WriteLine("Positive");
}
else
{
    Console.WriteLine("Negative");
}
```
Switch
```csharp
switch (day)
{
    case "Monday":
        Console.WriteLine("Start of week");
        break;
    default:
        Console.WriteLine("Another day");
        break;
}
```
Loops
For Loop
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```
While Loop
```csharp
int i = 0;
while (i < 5)
{
    Console.WriteLine(i);
    i++;
}
```
Do-While Loop
```csharp
Copy
Edit
do
{
    Console.WriteLine(i);
    i++;
} while (i < 5);
```
🔧 Methods
```csharp

static int Add(int a, int b)
{
    return a + b;
}
```
Call with:

```csharp
int result = Add(2, 3);
```
👤 Classes and Objects

```csharp
class Car
{
    public string color;

    public void Drive()
    {
        Console.WriteLine("Driving");
    }
}

// Using the class
Car myCar = new Car();
myCar.color = "Red";
myCar.Drive();
```
🧰 Access Modifiers
|Modifier	|Description|
| -- | -- |
|public|	Accessible from anywhere
|private|	Accessible only within class
|protected|	Accessible within class & derived
|internal|	Accessible within same assembly

⚙️ Common Keywords
|Keyword|	Description|
| -- | -- |
|class	|Declares a class|
|static|	Belongs to the type, not an instance
|void|	No return value
|return|	Returns a value
|new|	Creates an object
|this|	Refers to current instance
|namespace|	Groups related classes
|using|	Imports namespaces

🖨 Console Input / Output
```csharp
Console.WriteLine("Hello");
Console.Write("Enter name: ");
string name = Console.ReadLine();
```
📌 Arrays
```csharp
int[] numbers = { 1, 2, 3 };
Console.WriteLine(numbers[0]); // 1
```
🔁 Foreach Loop
csharp
Copy
Edit
foreach (int num in numbers)
{
    Console.WriteLine(num);
}
🧠 Null Safety
```csharp
string? name = null; // nullable
if (name != null)
{
    Console.WriteLine(name.Length);
}
```
📚 LINQ (Quick Example)
```csharp
using System.Linq;

int[] nums = {1, 2, 3, 4};
var evens = nums.Where(n => n % 2 == 0);

foreach (var n in evens)
    Console.WriteLine(n);
```
