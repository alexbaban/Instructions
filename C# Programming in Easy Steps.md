# C# Programming in Easy Steps

## Get started with .NET in 10 minutes

download and install the Microsoft .NET Core SDK   
(https://www.microsoft.com/net/learn/get-started/windows)

verify (at command prompt)   
`dotnet --version`

Hello World! console application

``` cmd

cd C:\apps
dotnet new console -o DotNetHello
cd DotNetHello
code .

```

open "Integrated Terminal" (from Visual Studio Code)   
`dotnet run`

create .exe   
`dotnet publish -c Release -r win10-x64`

## First program (file Program.cs)

``` c#
using System;

namespace DotNetHello
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            Console.ReadKey();
        }
    }
}

```
