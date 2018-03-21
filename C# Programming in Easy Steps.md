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

Open "Integrated Terminal"   
`dotnet run`

Create .exe   
`dotnet publish -c Release -r win10-x64`
