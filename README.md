# Demo project with ASP.NET, React and Postgres database

A demo project created by following [this tutorial](https://www.youtube.com/watch?v=2Ayfi7OJhBI).

## Local environment for this to work
```
> dotnet --version
6.0.201
> psql --version
psql (PostgreSQL) 14.2
> npm --version
8.5.4
```

## To run this repo
First, create a local postgres database with the details in `appsettings.Development.json` -> ConnectionStrings -> DefaultConnection.
( For the detail steps of creating database, refer to the above youtube tutorial starting from 5:35 )


Then, download the dotnet-ef tool for setting up the database:

```
dotnet tool install --global dotnet-ef
```

Then, create table in your database with below commands:

```shell
dotnet ef migrations add InitialCreate --context MyDbContext
dotnet ef database update --context MyDbContext
```

After that, install the needed packages
```
cd ClientApp
npm install
cd ..
dotnet restore
```


Finally, run `dotnet run` to start the server.

### What should happen

1. A web server started at localhost:44434


2. A restful API server responds to GET request to localhost:7067/api/Notes
   (Other endpoints can be found in Controllers/NotesControllers.cs)


### Memo of other commands used:
The command tool to auto generate controller codes:
```
dotnet tool install --global dotnet-aspnet-codegenerator
```

Dotnet restore should install the below pacakges. See reactnet.csproj:
```
dotnet add package Microsoft.EntityFrameworkCore.Design --version 6.0.3
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 6.0.2
```