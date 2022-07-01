# BuberDinner
A .net project emulating uber but for dinners. Project is used to learn about .net sdk and projects

Commands ran:
```bash
dotnet new sln
dotnet new webapi -o BuberDinner.API
dotnet new classlib -o BuberDinner.Contracts
dotnet new classlib -o BuberDinner.Infrastructure
dotnet new classlib -o BuberDinner.Application
dotnet new classlib -o BuberDinner.Domain

dotnet sln add BuberDinner.API/BuberDinner.API.csproj BuberDinner.Application/BuberDinner.Application.csproj BuberDinner.Contracts/BuberDinner.Contracts.csproj BuberDinner.Domain/BuberDinner.Domain.csproj BuberDinner.Infrastructure/BuberDinner.Infrastructure.csproj
```