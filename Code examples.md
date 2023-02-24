But first, how to upload code to github

first, use git init to initialize an empty repo in terminal, inside the folder with the content to upload 
then use git add -A
git commit -m "a message here"
git push
if prompted, git push --set-upstream origin main

When updating github, you don't need to do init, and should not need to do upstream again


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

**Classes**

Classes are basically custom data types, capable of doing many things. These classes operate on objects, which are instances of this class. It's common practice to create classes in a different file, for the sake of readability.

To create a class, you would first of all right click your project name in solution explorer, select add, then class, and give the class a name. This will set up an empty class file. The syntax would look like this:
```c#
//the internal keyword means that the class cannot be accessed from another project in the solution. While creating a class file will include this per default, it's not necessary. You can just use class Name. In single project solution, its basically same as public.
internal class Katt
{

}
//then, to add to this class, you would first choose wether the field would be private or public, then the data type, and finally the name of said attribute, naturally within the body {}
public string fluffiness;

//this will create a field named fluffiness. To then use it in your main file, you would create an object and then call upon the property using a .
Katt myKatt = new Katt();

myKatt.fluffiness = "Very":

//this will assign a string to the field that can then be used.



```

**Constructors**

Constructors are methods for classes. Their structure works like one, too.
```c#
public Name(string name)
{
    //inside here, you may add whatever you wish to add to the class. For instance, if you were to add this function, then "Hello" would be printed out for every object, first in order. The name of the constructor must match that of the class, which it exists inside of. 
    Console.WriteLine("Hello");
}
    //However, you may also add to the constructor parameters. If you were to add string name to them then you would add a new variable.
//This would then be invoked in the object, like a method.
Katt myKatt = new Katt("Cumma");
//We have now decided what the name will be. However, if we wish to use it then we must do so inside the actual constructor.
public Name(string name)
{
   Console.WriteLine(name);
   //this can be concatenated with other things, like strings. It's basically building with code.
}

```

Another way to do the same thing is to add fields to the constructor instead. This will allow the user to pass in what the fields will contain inside the object parameters.

```c#
            Katt kittykatt = new Katt();
            kittykatt.author = "Me :3";
            kittykatt.Title = "Limsa memories";
            kittykatt.pages = 666;

            Console.WriteLine(
            $"Author: {kittykatt.author}\n" +
            $"Title: {kittykatt.Title}\n" +
            $"Pages: {kittykatt.pages}");

```
Instead of doing this, the following can be changed.
```c#
//from

internal class Katt
    {
        public string Title;
        public string author;
        public int pages;

        public Katt(string aTitle, string aAuthor, int aPages) 
        {
            
        }
    }
```

```c#
//to
internal class Katt
    {
        public string Title;
        public string author;
        public int pages;

        public Katt(string aTitle, string aAuthor, int aPages) 
        {
            Title = aTitle;
            author = aAuthor;
            pages = aPages;
        }
    }
```
This allows the user to pass in each field inside object parameters
So instead of the previous class structure, we'd have
```c#
             Katt kitty = new Katt(
            "Bunny enthusiast",
            "How to properly eat rabbits",
            699);

```
This will produce the same result, except the user is now allowed to pass in whatever they want, as long as its the correct data types.

Put all together, the end result will look like this 
https://cdn.discordapp.com/attachments/1043148467628933161/1077930915394768896/image.png main file
https://cdn.discordapp.com/attachments/1043148467628933161/1077931263563931648/image.png class file

Multiple constructors can be created.

**The dot**

It's important to be able to access members of a class. Members are functions written into a class, such as methods. To do this, you would first enter the name of your object, followed by a dot, and then the name of the member.
An easy example would be 
```c#
var number = 5; 
var numberAsText = number.ToString();
```

first variable is an integar. In C#, all data types are classes, meaning they have built in methods. For exmple, ToString converts int into a string. The same structure works for anything not restricted by an access modifier.

It's also possible to access members on the same line that the object is created.

```C#
var classy = new ClassName().Method()
```

The downside to this is that there is no reference. You cannot save the object in a variable and access it later in this way. Also, var can stand in for any data type, so in order to keep the code flexible, its being used here so the compiler can figure out what it stands in for.

**Getters and setters**

These are called properties. Common practice is to use these in place of fields if you just wish to make something public in general. However, for many reasons you may want to make certain fields private. The way you would go about this is by using the same field structure but using private instead of public. This now means that particular field cannot be accessed from outside of the class.

To make this accessible, we would use something called a getter.
```c#
private string myProperty; 
public string thisProperty { get { return myProperty; } }
```
This means this field can now be accessed from outside the class, using the get property, that has been informed what should be returned. That being said, the whole reason we made the field private was to prevent undue outside tampering. You can use the set; property to determine what the field can be used for. Say for example that we wanted to create ratings for movies. We would then do it like this
```c#
 internal class Movies
    {
        public string title;
        public string director;
        private string rating;

        public Movies(string aTtitle, string aDirector, string aRating) 
        {
            title = aTtitle;
            director = aDirector;
            Rating = aRating;
        }

        public string Rating
        {
            get { return rating; }
            set {
                if(value == "nsfw" || value == "SFW") 
                {
                    rating = value;
                }
                else 
                {
                    rating = "NR";
                }
            }
        }
    }
```
With this code, there are only two ratings that can be printed out by using Rating. If any other rating is set, then NR will be printed out instead. This is why you would use fields in the first place.
Ultimately, get; and set; are methods with a fancy declaration, used to create fields in the background, hence why said fields can be skipped in favor of properties, unless when used like in the above example. While they are methods, they operate like fields, meaning they don't use ()

The dot adds separation as well. What happens in the above example is that whatever is before the dot is executed first, then whatever is returned is being acted upon when executing the right side of the dot. It always goes from left to right. So in addition to giving you access to whatever isn't restricted by an access modifier, . also dictates stages of execution and returned values. You will see everything you can access using . in intellisense.

In proper C# coding, there is always a field involved in classes, just often in the background.
For instance, this code will generate a private string field in the background using public properties. This isn't of much weight, since this doesn't give you access to this private string field, rather, it is generated at the time of compilation. We just work with the property itself. 

```C#
public class ClassName
{
   public string Name { get; set; }
}
```
If wishing to give the getter and the setter additional instructions, they will need their own brackets for this, but like in the below example, they will always remain inside the brackets of the field itself.

Ultimately, the relationship between getter, setter, and the methods you add works as so;
get is executed when accessing the property, set is executed when writing to the property.
Whatever you do inside these methods is up to you, but they are pretty much always used to read and write to a private field with some optional side effects.

**Throw**

Code have to account for every possible outcome. An outcome that is not handled will result in a crash. To this end, there is the keyword throw, which is used to create instructions on what to do in such cases. In this example, a string of text will be generated if you attempt to set the value of the field to null, which is your way to handle that particular exception.
```C#
namespace kittymessing
{
    public class testclass
    {
        private string _name;
        public string Name 
        {
            get { return _name; }
            set 
            {
                if(value == null) 
                {
                    throw new ArgumentNullException("You tried to assign null"); 

                    _name = value;
                }
            }
        }
        
    }
}
```
To then trigger that specific scenario, you would create an object in the main file and assign this field to null. 
```C#
testclass thisClass = new testclass();
thisClass.Name = null;
```

It's important to remember what does what. This code contains 3 properties that can all be accessed and found
```c#
        public string Rating { get; set; }
        public string Rating2 { get; private set; }
        public string Rating3 { get; }
```
The entire line is a property, so we have 3 properties. What enables them to be found outside the class is the public keyword on the left, but  if the getters were private it would be impossible to actually do something with them outside the class because they are not accessible outside the class.

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
