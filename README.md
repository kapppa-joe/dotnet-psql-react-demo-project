# Demo project with ASP.NET, React and Postgres database

A demo project created by following [this tutorial](https://www.youtube.com/watch?v=2Ayfi7OJhBI).

## Local Environment
> dotnet --version
6.0.201
> psql --version
psql (PostgreSQL) 14.2
> npm --version
8.5.4

# To run
First, create a local postgres database with the details in `appsettings.Development.json` -> ConnectionStrings -> DefaultConnection.

Then install the needed packages
```
cd ClientApp
npm install
cd ..
dotnet restore
```

Run `dotnet run` to start the server.
