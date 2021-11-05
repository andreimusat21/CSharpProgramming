# CSharpProgramming

# C# coding standards, conventions, and guidelines

* [Tour of C# language](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)
  - [Program structure](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/program-structure)
  - [Types and variables](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types-and-variables)
  - [Expressions](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/expressions)
  - [Statements](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/statements)
  - [Classes and objects](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/classes-and-objects)
  - [Structs](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/structs)
  - [Arrays](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/arrays)
  - [Interfaces](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/interfaces)
  - [Enums](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/enums)
  - [Delegates](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/delegates)
  - [Attributes](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/attributes)


## Table of contents

* [Programming Concepts](#programming-concepts)
  * [Asynchronous programming](#asynchronous-programming)


## Programming concepts

### Asynchronous programming
Used for
> I/O-bound needs (such as requesting data from a network, accessing a database, or reading and writing to a file system)
> CPU-bound code, such as performing an expensive calculation

Task-based Asynchronous Pattern (TAP): https://docs.microsoft.com/en-us/dotnet/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap

Download data from a web service:

    private readonly HttpClient _httpClient = new HttpClient();

    downloadButton.Clicked += async (o, e) =>
    {
        // This line will yield control to the UI as the request
        // from the web service is happening.
        //
        // The UI thread is now free to perform other work.
        var stringData = await _httpClient.GetStringAsync(URL);
        DoSomethingWithData(stringData);
    };

