# AdvanceConsole
🔥TobaFunction Is Best Library For Create Account Checker in C#🔥

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

