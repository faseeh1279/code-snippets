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


