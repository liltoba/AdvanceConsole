# AdvanceConsole
🔥Create Better Console App With AdvanceConsole c#🔥

# This Library
This Library Created for make better Console App💎

And this list is used in this library👇👇

🔺 ZimLabs.TableCreato
🔺 ConsoleMenu
🔺 Colorful.Console
🔺 Sharprompt

In This Library

# Basic Usage

```csharp
using System;
using System.Drawing;
using Console = Colorful.Console;
...
...
Console.WriteLine("console in pink", Color.Pink);
Console.WriteLine("console in default");
```




# Write With Full System.Drawing.Color Support

```csharp
int r = 225;
int g = 255;
int b = 250;
for (int i = 0; i < 10; i++)
{
    Console.WriteLine(storyFragments[i], Color.FromArgb(r, g, b));

    r -= 18;
    b -= 9;
}
```


# Format Text Using Two Colors

```csharp
string dream = "a dream of {0} and {1} and {2} and {3} and {4} and {5} and {6} and {7} and {8} and {9}...";
string[] fruits = new string[]
{
    "bananas",
    "strawberries",
    "mangoes",
    "pineapples",
    "cherries",
    "oranges",
    "apples",
    "peaches",
    "plums",
    "melons"
};

Console.WriteLineFormatted(dream, Color.LightGoldenrodYellow, Color.Gray, fruits);
```

# Format Text Using Several Colors

```csharp
string dream = "a dream of {0} and {1} and {2} and {3} and {4} and {5} and {6} and {7} and {8} and {9}...";
Formatter[] fruits = new Formatter[]
{
    new Formatter("bananas", Color.LightGoldenrodYellow),
    new Formatter("strawberries", Color.Pink),
    new Formatter("mangoes", Color.PeachPuff),
    new Formatter("pineapples", Color.Yellow),
    new Formatter("cherries", Color.Red),
    new Formatter("oranges", Color.Orange),
    new Formatter("apples", Color.LawnGreen),
    new Formatter("peaches", Color.MistyRose),
    new Formatter("plums", Color.Indigo),
    new Formatter("melons", Color.LightGreen),
};

Console.WriteLineFormatted(dream, Color.Gray, fruits);
```

# Alternate Between 2 or More Colors Based on Number of Console Writes

```csharp
ColorAlternatorFactory alternatorFactory = new ColorAlternatorFactory();
ColorAlternator alternator = alternatorFactory.GetAlternator(2, Color.Plum, Color.PaleVioletRed);

for (int i = 0; i < 15; i++)
{
    Console.WriteLineAlternating("cats", alternator);
}
```

# Alternate Between 2 or More Colors Based on 1 or More Regular Expressions

```csharp
ColorAlternatorFactory alternatorFactory = new ColorAlternatorFactory();
ColorAlternator alternator = alternatorFactory.GetAlternator(new[] { "hiss", "m[a-z]+w" }, Color.Plum, Color.PaleVioletRed);

for (int i = 0; i < 15; i++)
{
    string catMessage = "cats";

    if (i % 3 == 0)
    {
        catMessage = meowVariant[meowCounter++];
    }
    else if (i % 10 == 0)
    {
        catMessage = "hiss";
    }

    Console.WriteLineAlternating(catMessage, alternator);
}
```

# Style Specific Regions of Text

```csharp
StyleSheet styleSheet = new StyleSheet(Color.White);
styleSheet.AddStyle("rain[a-z]*", Color.MediumSlateBlue);

Console.WriteLineStyled(storyAboutRain, styleSheet);
```

# Style Specific Regions of Text, Performing a Simple Transformation

```csharp
StyleSheet styleSheet = new StyleSheet(Color.White);
styleSheet.AddStyle("rain[a-z]*", Color.MediumSlateBlue, match => match.ToUpper());

Console.WriteLineStyled(storyAboutRain, styleSheet);
```

# Style Specific Regions of Text, Performing a Transformation Based on Surrounding Text

```csharp
StyleSheet styleSheet = new StyleSheet(Color.White);
styleSheet.AddStyle("rain[a-z]*", Color.MediumSlateBlue,
    (unstyledInput, matchLocation, match) =>
    {
        if (unstyledInput[matchLocation.End] == '.')
        {
            return "marshmallows";
        }
        else
        {
            return "s'mores";
        }
    });

Console.WriteLineStyled(storyAboutRain, styleSheet);
```

# Convert Text to ASCII Art Using a Default Font

```csharp
int DA = 244;
int V = 212;
int ID = 255;
for (int i = 0; i < 3; i++)
{
    Console.WriteAscii("HASSELHOFF", Color.FromArgb(DA, V, ID));

    DA -= 18;
    V -= 36;
}
```

# Convert Text to ASCII Art Using FIGlet Fonts

```csharp
FigletFont font = FigletFont.Load("chunky.flf");
Figlet figlet = new Figlet(font);

Console.WriteLine(figlet.ToAscii("Belvedere"), ColorTranslator.FromHtml("#8AFFEF"));
Console.WriteLine(figlet.ToAscii("ice"), ColorTranslator.FromHtml("#FAD6FF"));
Console.WriteLine(figlet.ToAscii("cream."), ColorTranslator.FromHtml("#B8DBFF"));
```

# Style Collections With a Gradient

```csharp
List<char> chars = new List<char>()
{
	'r', 'e', 'x', 's', 'z', 'q', 'j', 'w', 't', 'a', 'b', 'c', 'l', 'm',
	'r', 'e', 'x', 's', 'z', 'q', 'j', 'w', 't', 'a', 'b', 'c', 'l', 'm',
	'r', 'e', 'x', 's', 'z', 'q', 'j', 'w', 't', 'a', 'b', 'c', 'l', 'm',
	'r', 'e', 'x', 's', 'z', 'q', 'j', 'w', 't', 'a', 'b', 'c', 'l', 'm'
};
Console.WriteWithGradient(chars, Color.Yellow, Color.Fuchsia, 14);
```



# Basic Menu:

```csharp
 string[] menuItems = new string[] { "Option 1", "Option 2", "Option 3", "Option 4" };

    Menu menu = new Menu(menuItems, "Main Menu");

    switch (menu.displayMenu())
    {
        case 1:
            Console.WriteLine("Option 1");
            break;
        case 2:
            Console.WriteLine("Option 2");
            break;
        case 3:
            Console.WriteLine("Option 3");
            break;
        case 4:
            Console.WriteLine("Option 4");
            break;
        default:
            break;
    }
```

# TableCreator:

```csharp
public sealed class Person
{
    // Align the text to the right
    [Appearance(TextAlign = TextAlign.Right)]
    public int Id { get; set; }

    // Set the name of the column to "First name"
    [Appearance(Name = "First name")]
    public string Name { get; set; }

    public string LastName { get; set; }

    public string Mail { get; set; }

    public string Gender { get; set; }

    [Appearance(Ignore = true)]
    public string JobTitle { get; set; }

    // Change the format of the DateTime value
    [Appearance(Format = "yyyy-MM-dd")]
    public DateTime Birthday { get; set; }
}

// Here a list with some persons...
var tempList = new List<Person>();

// Create a ASCII styled table with and show the row numbers
var result = TableCreator.CreateTable(tempList, OutputType.Default, true);
    }
```

# And the result looks like this:
```
+-----+----+------------+-------------+-------------------------------+--------+------------+
| Row | Id | First name | Last name   | E-Mail                        | Gender | Birthday   |
+-----+----+------------+-------------+-------------------------------+--------+------------+
|   1 |  1 | Tommy      | Giblin      | tgiblin0@amazon.co.uk         | Female | 1968-03-26 |
|   2 |  2 | Sven       | Puden       | spuden1@soundcloud.com        | Male   | 1952-04-24 |
|   3 |  3 | Garvy      | Czaple      | gczaple2@com.com              | Male   | 1965-04-10 |
|   4 |  4 | Eryn       | Mariotte    | emariotte3@issuu.com          | Female | 1986-07-23 |
|   5 |  5 | Zaccaria   | Oiseau      | zoiseau4@huffingtonpost.com   | Male   | 1967-11-09 |
|   6 |  6 | Conny      | Di Batista  | cdibatista5@mysql.com         | Male   | 1997-12-27 |
|   7 |  7 | Toma       | Tristram    | ttristram6@mashable.com       | Female | 1960-02-15 |
|   8 |  8 | Boniface   | Sperry      | bsperry7@behance.net          | Male   | 1985-05-13 |
|   9 |  9 | Nevins     | Stear       | nstear8@aboutads.info         | Male   | 1951-04-05 |
|  10 | 10 | Yolane     | Wadman      | ywadman9@stanford.edu         | Female | 1962-05-28 |
+-----+----+------------+-------------+-------------------------------+--------+------------+

```

# Simple input

```csharp
var name = Prompt.Input<string>("What's your name?");
Console.WriteLine($"Hello, {name}!");
```

# Password

```csharp
var secret = Prompt.Password("Type new password", new[] { Validators.Required(), Validators.MinLength(8) });
Console.WriteLine("Password OK");
```

# Confirmation

```csharp
var answer = Prompt.Confirm("Are you ready?");
Console.WriteLine($"Your answer is {answer}");
```

# Input

```csharp
var name = Prompt.Input<string>("What's your name?");
Console.WriteLine($"Hello, {name}!");

var number = Prompt.Input<int>("Enter any number");
Console.WriteLine($"Input = {number}");
```

# Select

```csharp
var city = Prompt.Select("Select your city", new[] { "Seattle", "London", "Tokyo" });
Console.WriteLine($"Hello, {city}!");
```

# Enum support

```csharp
var value = Prompt.Select<MyEnum>("Select enum value");
Console.WriteLine($"You selected {value}");
```

# MultiSelect (Checkbox)

```csharp
var cities = Prompt.MultiSelect("Which cities would you like to visit?", new[] { "Seattle", "London", "Tokyo", "New York", "Singapore", "Shanghai" }, pageSize: 3);
Console.WriteLine($"You picked {string.Join(", ", cities)}");
```

# List

```csharp
var value = Prompt.List<string>("Please add item(s)");
Console.WriteLine($"You picked {string.Join(", ", value)}");
```

# AutoForms (Preview)

```csharp
// Input model definition
public class MyFormModel
{
    [Display(Prompt = "What's your name?")]
    [Required]
    public string Name { get; set; }

    [Display(Prompt = "Type new password")]
    [DataType(DataType.Password)]
    [Required]
    [MinLength(8)]
    public string Password { get; set; }

    [Display(Prompt = "Are you ready?")]
    public bool Ready { get; set; }
}

var result = Prompt.AutoForms<MyFormModel>();
```

# Symbols

```csharp
Prompt.Symbols.Prompt = new Symbol("🤔", "?");
Prompt.Symbols.Done = new Symbol("😎", "V");
Prompt.Symbols.Error = new Symbol("😱", ">>");

var name = Prompt.Input<string>("What's your name?");
Console.WriteLine($"Hello, {name}!");
```

# Color schema

```csharp
Prompt.ColorSchema.Answer = ConsoleColor.DarkRed;
Prompt.ColorSchema.Select = ConsoleColor.DarkCyan;

var name = Prompt.Input<string>("What's your name?");
Console.WriteLine($"Hello, {name}!");
```

# Unicode support

```csharp
// Prefer UTF-8 as the output encoding
Console.OutputEncoding = Encoding.UTF8;

var name = Prompt.Input<string>("What's your name?");
Console.WriteLine($"Hello, {name}!");
```

# Cancellation support

```csharp
// Throw an exception when canceling with Ctrl-C
Prompt.ThrowExceptionOnCancel = true;

try
{
    var name = Prompt.Input<string>("What's your name?");
    Console.WriteLine($"Hello, {name}!");
}
catch (PromptCanceledException ex)
{
    Console.WriteLine("Prompt canceled");
}
```

# Supported platforms

```
◾️Windows
◾️Command Prompt
◾️PowerShell
◾️Windows Terminal
◾️Linux (Ubuntu, etc)
◾️Windows Terminal (WSL 2)
◾️macOS
◾️Terminal.app
```
