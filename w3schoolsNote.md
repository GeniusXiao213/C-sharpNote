# C# note

## Note from w3schools

using System; **//we can use classes from system namespace**

namespace HelloWorld  **//namespace is container for classes and other namespaces**

{

    class Program  **// container for data and methods**
    
    {
    
        static void Main(string[] args)
        
        {   
        
            Console.WriteLine("Hello World!");
            
        }
        
    }
    
}

---
int myNum = 5;               // Integer (whole number)

double myDoubleNum = 5.99D;  // Floating point number

char myLetter = 'D';         // Character

bool myBool = true;          // Boolean

string myText = "Hello";     // String


**remember to add suffix**

long myNum = 15000000000L;  

float=myNum = 5.75F;

double d1 = 12E4D;

---
### C# Type Casting
1. Type casting is when you assign a value of one data type to another type.

In C#, there are two types of casting:

Implicit Casting (automatically) - converting a smaller type to a larger type size
**char -> int -> long -> float -> double**

Explicit Casting (manually) - converting a larger type to a smaller size type
double -> float -> long -> int -> char

int myInt = 9;

double myDouble = myInt;       **// Automatic casting: int to double**

double myDouble = 9.78;

int myInt = (int) myDouble;    **// Manual casting: double to int**

2. Type Conversion Methods
It is also possible to convert data types explicitly by using built-in methods, 

such as Convert.ToBoolean, Convert.ToDouble, Convert.ToString, Convert.ToInt32 (int) and Convert.ToInt64 (long):

---

Console.WriteLine() is used to output (print) values. Now we will use Console.ReadLine() to get user input.


// Type your username and press enter
Console.WriteLine("Enter username:");

// Create a string variable and get user input from the keyboard and store it in the variable
string userName = Console.ReadLine();

// Print the value of the variable (userName), which will display the input value
Console.WriteLine("Username is: " + userName);

---
### Math

The Math.Max(x,y) method can be used to find the highest value of x and y

The Math.Min(x,y) method can be used to find the lowest value of of x and y

The Math.Sqrt(x) method returns the square root of x

The Math.Abs(x) method returns the absolute (positive) value of x

Math.Round() rounds a number to the nearest whole number

---

### String

**String Length**

the length of a string can be found with the Length property:

string txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

Console.WriteLine("The length of the txt string is: " + txt.Length);

ToUpper() and ToLower(), which returns a copy of the string converted to uppercase or lowercase:

string txt = "Hello World";

Console.WriteLine(txt.ToUpper());   // Outputs "HELLO WORLD"

Console.WriteLine(txt.ToLower());   // Outputs "hello world"

**String Concatenation**

1. string firstName = "John ";

string lastName = "Doe";

string name = firstName + lastName;

Console.WriteLine(name);

2. You can also use the string.Concat() method to concatenate two strings:

string name = string.Concat(firstName, lastName);

Console.WriteLine(name);

3. Another option of string concatenation, is string interpolation, which substitutes values of variables into placeholders in a string.

Note that you do not have to worry about spaces, like with concatenation:

string name = $"My full name is: {firstName} {lastName}";

Console.WriteLine(name);

**Access String**

You can find the index position of a specific character in a string, by using the IndexOf() method:

string myString = "Hello";

Console.WriteLine(myString.IndexOf("e"));  // Outputs "1"

Another useful method is Substring(), which extracts the characters from a string, starting from the specified character position/index, 

and returns a new string. 

This method is often used together with IndexOf() to get the specific character position:

// Full name

string name = "John Doe";

// Location of the letter D

int charPos = name.IndexOf("D");

// Get last name

string lastName = name.Substring(charPos);

// Print the result

Console.WriteLine(lastName);

---

### Sepecial Characters

<img width="596" alt="image" src="https://user-images.githubusercontent.com/100718931/201483394-08ccc41a-d8d5-4368-aa74-05d4241aeedc.png">

string txt = "We are the so-called \"Vikings\" from the north.";

string txt = "It\'s alright.";

<img width="244" alt="image" src="https://user-images.githubusercontent.com/100718931/201483495-2f082e70-8d4a-40b5-afd2-edb006390feb.png">

---

**The else if Statement**

Use the else if statement to specify a new condition if the first condition is False.

if (condition1)

{

  // block of code to be executed if condition1 is True
  
} 

else if (condition2) 

{

  // block of code to be executed if the condition1 is false and condition2 is True
  
} 

else

{

  // block of code to be executed if the condition1 is false and condition2 is False
  
}

**ternary operator**

variable = (condition) ? expressionTrue :  expressionFalse;

int time = 20;

string result = (time < 18) ? "Good day." : "Good evening.";

Console.WriteLine(result);

**switch**

switch(expression) 

{

  case x:
  
    // code block
    
    break;
    
  case y:
  
    // code block
    
    break;
    
  default: **The default keyword is optional and specifies some code to run if there is no case match**
  
    // code block
    
    break;
    
}

---

**The foreach Loop**

There is also a foreach loop, which is used exclusively to loop through elements in an array:

foreach (type variableName in arrayName) 

{

  // code block to be executed
  
}

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

foreach (string i in cars) 

{

  Console.WriteLine(i);
  
}

---

## Break and Continue

**The break statement can also be used to jump out of a loop.**

**The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.**

for (int i = 0; i < 10; i++) 

{

  if (i == 4) 
  
  {
  
    continue;
    
  }
  
  Console.WriteLine(i);
  
}

output: 0,1,2,3,5,6,7,8,9

---

## Arrya

**Creating an array**

1. string[] cars;

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

2. // Create an array of four elements, and add values later

string[] cars = new string[4];

3. // Create an array of four elements and add values right away 

string[] cars = new string[4] {"Volvo", "BMW", "Ford", "Mazda"};

4. // Create an array of four elements without specifying the size 

string[] cars = new string[] {"Volvo", "BMW", "Ford", "Mazda"};

5. // Create an array of four elements, omitting the new keyword, and without specifying the size

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

However, you should note that if you declare an array and initialize it later, you have to use the new keyword:

// Declare an array

string[] cars;

// Add values, using new

cars = new string[] {"Volvo", "BMW", "Ford"};

**Loop Through a array**

1. for loop

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

for (int i = 0; i < cars.Length; i++) 

{

  Console.WriteLine(cars[i]);
  
}

2. foreach loop

string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

foreach (string i in cars) 

{

  Console.WriteLine(i);
  
}

**sort array**

Array.Sort(cars);

foreach (string i in cars)

{

  Console.WriteLine(i);
  
}

output: small->big

<img width="605" alt="image" src="https://user-images.githubusercontent.com/100718931/201484547-5eeb57f0-c01a-4eed-933d-67b3ff3dd5fc.png">

**loop through a 2D array**

1. <img width="566" alt="image" src="https://user-images.githubusercontent.com/100718931/201484602-4cde5e7f-6253-41c1-9da7-28fa9ff37aca.png">

2. <img width="604" alt="image" src="https://user-images.githubusercontent.com/100718931/201484615-6e8e619d-338c-4dc3-bc02-c13cb2c0be26.png">



