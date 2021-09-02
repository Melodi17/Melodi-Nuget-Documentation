## Melodi.IO

### Tables

**Overview:** This is a small class for drawing tables in console

```c#
TableBuilder t = new();
t.AddRow("Username", "Email");
t.AddRow("--------", "-----");

t.AddRow("testuser", "testuser@gmail.com");
t.AddRow("foobar", "foobar@hotmail.com");

Console.WriteLine(t.Output());
```

**Credit:** This code was remixed from https://stackoverflow.com/users/497374/nick on stack overflow

### SmartReader

**Overview:** A class for reading lines (I made this because all the built-ins are annoying)

**Information:** It will only split a string by **\n** characters

```c#
SmartReader sr = new("Hello\nWorld");
Console.WriteLine(sr.ReadLine()); // Outputs Hello
Console.WriteLine(sr.PeekLine()); // Outputs World (Doesn't dispose line)
Console.WriteLine(sr.ReadLine()) // Outputs World
```

**Credit:** Thanks to the annoying built-in libraries for motivating me to make this

### SmartLogger

**Overview:** A logging class for showing output

```c#
SmartLogger sl = new(LogLevel.Trace);
sl.Log(LogLevel.Debug, "Started!");
```

