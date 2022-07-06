# BuberDinner
A .net project emulating uber but for dinners. Project is used to learn about .net sdk and projects

### Following the tutorial:
https://www.youtube.com/watch?v=fhM0V2N1GpY

Commands ran (Project is built on linux)
```bash
dotnet new sln
dotnet new webapi -o BuberDinner.API
dotnet new classlib -o BuberDinner.Contracts
dotnet new classlib -o BuberDinner.Infrastructure
dotnet new classlib -o BuberDinner.Application
dotnet new classlib -o BuberDinner.Domain

dotnet sln add BuberDinner.API/BuberDinner.API.csproj BuberDinner.Application/BuberDinner.Application.csproj BuberDinner.Contracts/BuberDinner.Contracts.csproj BuberDinner.Domain/BuberDinner.Domain.csproj BuberDinner.Infrastructure/BuberDinner.Infrastructure.csproj
```
Testing using: dotnet build

Part2: Dependencies between projects:
APi needs to know about contracts and application layer
```bash
dotnet add BuberDinner.API/ reference BuberDinner.Contracts/ BuberDinner.Application/
```

Infrastructure needs to know about application
```
dotnet add BuberDinner.Infrastructure/ reference BuberDinner.Application/
```

Application needs to know about the domain
```
dotnet add BuberDinner.Application/ reference BuberDinner.Domain/
```

API needs to know about the infrastructure
```
dotnet add BuberDinner.API/ reference BuberDinner.Infrastructure/
```

<br>
Part3: Installing rest client extention via VSCODE and checking to make sure this works:
```bash 
dotnet build
``` 

Running specifically the API allows with the dotnet command lets you test the api in isolation:
```
dotnet dotnet run --project BuberDinner.API/
```
And you get an output like this, which has the API endpoint/route to use to test the API:
```bash
Building...
info: Microsoft.Hosting.Lifetime[14]
      Now listening on: https://localhost:7191
info: Microsoft.Hosting.Lifetime[14]
      Now listening on: http://localhost:5198
info: Microsoft.Hosting.Lifetime[0]
      Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
      Hosting environment: Development
info: Microsoft.Hosting.Lifetime[0]
      Content root path: /home/sandesh/Documents/REPOS/BuberDinner/BuberDinner.API/
```