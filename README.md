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

part2: Dependencies between projects:
APi needs to know about contracts and application layer
```bash
dotnet add BuberDinner.API/ reference BuberDinner.Contracts/ BuberDinner.Application/
```

Infrastructure needs to know about application
dotnet add BuberDinner.Infrastructure/ reference BuberDinner.Application/