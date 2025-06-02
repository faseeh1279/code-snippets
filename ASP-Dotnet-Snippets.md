# Important ASP .NET Core Web API Commands. 

### Steps for `Downloading` ASP .NET Core 

#### 1. Create a new .NET Core Project 
```bash 
dotnet new webapi -n MyApiProject
```

#### 2. Run the Project 
```bash 
dotnet run 
```

#### 3. Create & Add Migrations &  Apply the Migrations 
```bash
dotnet ef migrations add "Initial Create"
dotnet ef database update
```



#### 4. Necessary Packages for Working With ASP .Net Core Database SQL Server 
#### Microsoft.EntityFrameworkCore.SqlServer
#### Microsoft.EntityFrameworkCore.Tools
#### Microsoft.EntityFrameworkCore.Design

#### 5. Launch https Port for Running dotnet project from Visual Studio Code
```bash 
dotnet run --launch-profile https
```