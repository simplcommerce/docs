# Working with databases

---

SimplCommerce supports many database engines. We have tested with SQL Server, PostgreSQL, SQLite. Generaly, it can work with any database that Entity Framework Core supports. See [Entity Framework Core providers](https://docs.microsoft.com/en-us/ef/core/providers/index)

SimplCommerce supports SQL Server by default. There a couple of changes need to be made in order to swich to another database engine.

- Add package reference to the database provider you would like to use in the SimplCommerce.WebHost.csproj

- Update the code to use your the new provider in Program.cs

```csharp
configBuilder.AddEntityFrameworkConfig(options =>
    options.UseSqlServer(configuration.GetConnectionString("DefaultConnection"))
);
```
and in SimplCommerce.WebHost/Extensions/ServiceCollectionExtensions.cs

```csharp
services.AddDbContextPool<SimplDbContext>(options =>
    options.UseSqlServer(configuration.GetConnectionString("DefaultConnection"),
        b => b.MigrationsAssembly("SimplCommerce.WebHost")));
return services;
```

- Update the connection string in the appsettings.json to your database engine

- Delete all the existing migration code in the 'Migrations' folder in the SimplCommerce.WebHost project. Because the database migration code are generated differently from one to another database provider

- Run 'Add-Migration \<NameOfMigration\>' in Package Management Console or 'dotnet ef migrations add \<NameOfMigration\>' in the command line

- Run 'Update-Database' in the Package Management Console or 'dotnet ef database update' in the command line

We encourage you to keep track the generated code in the Migrations folder in source control so that you can do the migration on your existing database later. When you want to do migration on existing database, get the latest MigrationId in '__EFMigrationsHistory' table. Then restore the Migration code back to that snapshot. Then you can do 'Add-Migration' from there. Entity Framework will detect changes since that snapshot