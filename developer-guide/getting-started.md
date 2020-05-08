# Getting Started

---

## Docker

For testing purpose only `docker run -p 5000:80 simplcommerce/ci-build`

## Visual Studio 2017 and SQL Server

#### Prerequisites

- SQL Server
- [Latest visual Studio 2019 (version >= 16.4) with .NET Core SDK 3.1](https://www.microsoft.com/net/download/all)

#### Steps to run

- Update the connection string in appsettings.json in SimplCommerce.WebHost
- Build whole solution.
- Make sure your startup project is SimplCommerce.Webhost(Right-click on SimpleCommerce.Webhost and select "Set as startup project").     Otherwise the next step will fail with a dbcontext missing error. 
- Open Package Manager Console Window and type "Update-Database" then press "Enter". This action will create database schema.
- In Visual Studio, press "Control + F5".
- The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!

## Mac/Linux with PostgreSQL

#### Prerequisite

- PostgreSQL
- [.NET Core SDK 3.1](https://www.microsoft.com/net/download/all)

#### Steps to run

- Update the connection string in appsettings.json in SimplCommerce.WebHost.
- Run file "sudo ./simpl-build.sh".
- In the terminal, navigate to the "src/SimplCommerce.WebHost" type "dotnet run" and hit "Enter".
- Open browser, open http://localhost:5000. The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!
