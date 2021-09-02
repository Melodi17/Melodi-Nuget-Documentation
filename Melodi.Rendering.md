## Melodi.Rendering

### Point (NativeMethods)

**Overview:** Stores positioning data (x, y)

```c# 
Point p = new(1, 1);
Console.WriteLine($"x:{p.x} y:{p.y}"); // Returns x:1 y:1
p = p.OffSet(1, -1);
Console.WriteLine($"x:{p.x} y:{p.y}"); // Returns x:2 y:0
```

### Size (NativeMethods)

**Overview:** Stores positioning data (x, y)

```c# 
Point p = new(1, 1);
Console.WriteLine($"x:{p.x} y:{p.y}"); // Returns x:1 y:1
p = new Size(1, 1).ToPoint(p);
Console.WriteLine($"x:{p.x} y:{p.y}"); // Returns x:2 y:2
```

### Grid\<T\> (NativeMethods)

**Overview:** Stores a 2D array cleanly

```c# 
Grid<char> g = new(10, 10);
g[new Point(1, 1)] = 'a';
foreach ((Point, char) item in g.Foreach())
{
    if (item.Item2 == 'a')
    {
        Console.WriteLine($"Found the a character at x:{item.Item1.x} y:{item.Item1.y}")
    }
}
```

### ConsoleRenderer (NativeMethods)

**Overview:** Initializes the console for ANSI output

```c# 
Console.WriteLine("\x1b[31mHello\x1b[0m"); //Prints '\x1b[31mHello\x1b[0m'
ConsoleRenderer.Init();
Console.WriteLine("\x1b[31mHello\x1b[0m"); //Prints 'Hello' in red
```

### ConsoleListener (ConsoleLib)

**Overview:** I haven't had time to fully document this yet, I will try soon though
