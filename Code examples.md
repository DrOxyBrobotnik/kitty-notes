But first, how to upload code to github

first, use git init to initialize an empty repo


Data types: https://www.tutorialsteacher.com/csharp/csharp-data-types

There are many datatypes in C#. While it's possible to create your own functions by using classes, there are many pre-defined data types. 

String - simply a string of characters, denoted by "". For instance
```c#
Console.Write("Hello world");
```
would simple print out "Hello world" when compiled.

int - this is the data type to use when working with numbers, similar to string being the data type for string of characters. A simple example would be 
```c#
int a = 2;
int b = 3;

Console.Write(a + b);
```
Each int has to be given a value, unless used in a method, in which case the value would be determined in the invocation instead.

bool - this is basically true or false.  By using this, you are creating a simple two case scenario. This is useful because it allows you to easily return something. For instance
```c#
bool b;
int a;

if (b)
return a;
```

Normally you would need to create ways to handle if something resolves to true or false, by using the true and false keywords. However, the boolean datatype will always result in true or false, so that is in itself covered. Hence, you can simplify the process a lot. Of note is that return can be used to print text to the console, instead of Console.Write();, by using return "";

return - the return keyword is used to tell the compiler what you want to return - everything ultimately has to culiminate into something, to control where that happens, you use this. Example is not neccessary since I've already used this prior. 

var - var stands for variable. You can use this in place of any data type, since if you have a complete string of code, then Visual Studio will understand what the correct data type is. If you are unsure what data type to use, use this, and if that doesn't work, specify. However, figuring it out on its own is extra work for the compiler, so for the sake of time, its better to specify the data type.

Arrays - box with data types in it, defined first.
```c#
int[] name = new int[5];
//creates an array that can hold 5 ints at the most
var values = new int [100];
//this does the same thing, and is faster to type. A good use of the var keyword.
```
Regular arrays are good for when you don't know what the numbers are going to be. It's an empty box with storage spaces, waiting to be filled. Of note is that each array can only contain one data type. Also, to access the length of an array, you need .Length

There is another way to make an array. It's faster and good for when you know what all the values will be. 
```c#
int[] kattnumbers = { 1, 2, 3, 4, 5}
```
Ultimately, both ways have their usages. Regardless, make sure to match up your variable type to what the array will contain. Array indexes starts at 0.

Another important thing - joining strings. While you can display each element of an array one at a time, doing so is cumbersome. It's much better to use the built in method Join. To do this, you would...
```c#
int[] kattnumbers = { 1, 2, 3, 4, 5 };

Console.WriteLine(string.Join(',', kattnumbers));
```
To do this, you must specify what the separator between each element would be. even if its just a blank space. This separator goes between the '', and is then separate from the collection name with a , - this will, in this case, generate 1,2,3,4,5. A space could be used in place of , for no commas.


Also, example code for an array inside a for loop
```c#
int[] luckyNumbers = { 4, 8, 15, 16, 23, 42 };
            
            for(int i = 0; i < luckyNumbers.Length; i++) 
            {
                Console.WriteLine(luckyNumbers[i]);
                
            }

            Console.ReadLine();
```

**If scenarios**

If scenarios allows you to create different outcomes. This follows a syntax of condition, and then body. For instance, a variable can be used to create this liks so:
```c#
string lottery;
string win = "OH MY GOD!"
string lose = "Noooo..."
if (lottery == win)
    Console.WriteLine(win)
else 
{
    Console.WriteLine(lose);
}

```

You can also use if else, this is handy when you want to create multiple scenarios. Else can have an empty body if that covers the scenario where no choice was made, since every choice has to be accounted for, else the program will crash.

**Loops**

Loops is a way to make the execution of a specific block of code repeat until a condition is met. This is the same kind of logic you would see in calculators. When you divide by 0 and it says "error" that doesn't mean the calculator crashed, it means it displayed whatever was inside the body of the if condition and then looped back to start. There are several kinds of loops. The while loop will repeat its code until the condition is false, which will result in the code being skipped over.
```c#
int index = 1; //sets a starting value in our case
while(index <= 5);//the condition to be looped
{ 
Console.WriteLine(index); //prints out what index returns
index++;//the counter to stop it from printing 1 forever
}
```
This will write out an incrementing number, so with this condition, 1 2 3 4 5.
There is also the do while loop. What this does it executing the code before the loop at least once before looping a contition.
```c#
int index = 6;
do
{
   Console.WriteLine(index);
   index++;
}while (index <= 5);
```
This will print 6 once, even though the condition resolve to false. The structure is a bit jank, but you get used to it ig...

Then there is the for loop. This one just loops 

**Methods and invocations**

Methods are basically something that can accept user input rather than working with hard coded values, such as a string or an int. It has three critical properties - return types, name, and arguments. An easy method would look something like this.

```c# 
//of critical note is that you cannot both use the void type and a return
//type together. You either return something or nothing. Methods always have //return type (or void if no return), method name, //parameters in ()
//regardless, just looking at the line containing
//the method name should be all you need to know what it does and be able
//to use it
 void Numbahs(int stuff)
            {
                if (stuff == 69)
                {
                    Console.WriteLine("Lol, leet number");
                }

                else
                {
                    Console.WriteLine("You fail");
                }


            }
```

and then to invoke it, above it we would simply use the name and then pass something of the same data type as the argument inside the parameters, like so
```c#
Numbahs(14);
```
In so doing, we allow the user to enter whatever they want of the compatible data types. This is much more flexible. 

```c#
string MethodExample(string katt1, string katt2)

{
   if (katt1 == katt2)

   return "Two katts UwU";

   else 

   return "One katt is sus";
}
```

How to count legs of animals:

```c#
public int Invoke(int chickenCount, int cowCount, int pigCount)
{
   var totalcount = 0;

   var chickenLegs = chickenCount <= 0 ? 0 chickenCount * 2;
   var cowLegs = cowCount <= 0 ? 0 cowCount * 4;
   var pigLegs = pigCount <= 0 ? 0 pigCount * 4;

   totalCount = chickenLegs + cowLegs + pigLegs;

   return totalCount
}
```

Process: a method is made with 3 variables passed as arguments, then a new variable is created inside the method, this will be our final variable that we use to return the total sum. Three new variables are then made, and assigned to the variables we passed as arguments. Then each line checks if the total amount is equal to or less than 0, in which case 0 will be returned, otherwise the amount times the integer will be returned, in our case times two for chicken, times four for cow or pig.
totalCount is then assigned the value of each variable responsible for counting the legs put together, and then finally returned.         

**Calculators**

The basic stuff that tests what you have learned. Here is a very basic calculator that can handle plus and decimals 
```c#
{
            Console.Write("Enter a number: ");
            double num1 = Convert.ToDouble(Console.ReadLine());
            Console.Write("Enter second number: ");
            double num2 = Convert.ToDouble(Console.ReadLine());

            Console.WriteLine(num1 + num2);


            Console.ReadLine();
        }
```

Normally, you can't convert string to int directly, so using int name = Console.ReadLine would not work. However, you can add convert to solve that problem. Double was used here, but you can convert to many things, like just ToInt32 if you don't want to work with decimals.

Here is a much better calculator 
```c#
double x = Convert.ToDouble(Console.ReadLine());
        double y = Convert.ToDouble(Console.ReadLine());
        Console.WriteLine("Enter your operator(+, -, /, *)");
        var myOperator = string.Empty;

            while (myOperator != "+" &&
            myOperator != "-" &&
            myOperator != "/" &&
            myOperator != "*" ||
            myOperator == "/" && y == 0)

        {
            Console.WriteLine("Please choose a valid operand");
            myOperator = Console.ReadLine();
        }
            if (myOperator == "+")
            Console.WriteLine(x + y);
            
            if (myOperator == "-")
            Console.WriteLine(x - y);

            if (myOperator == "*")
            Console.WriteLine(x * y);
            
            if (myOperator == "/")
            Console.WriteLine(x / y);
```

This calculator can accept all the basic operators you would expect it to, handle decimals, and won't crash if you try to divide by zero. It also shows off the power of strings as more than just printing text to the console. 
Also, here's a simple madlibs to reinforce how reading user input works 
```c#
string color, pluralNoun, awfulPlace;

            Console.Write("Enter a color: ");
            color = Console.ReadLine();

            Console.Write("Enter a plural noun: ");
            pluralNoun = Console.ReadLine();

            Console.Write("Enter an awful place: ");
            awfulPlace = Console.ReadLine();

            Console.WriteLine("Roses are " + color);
            Console.WriteLine(pluralNoun + " are blue ");
            Console.WriteLine("I'm stuck on the " + awfulPlace + " AND SO ARE FUCKING YOU!");

            Console.ReadLine();
```
