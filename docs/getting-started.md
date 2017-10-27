# Getting Started

---

## Docker
- First run the database: `docker run --name simpldb -d postgres`
- Then run the app: `docker run --name simplsite -d -p 5000:5000 --link simpldb:simpldb simplcommerce/nightly-build`

## Visual Studio 2017 and SQL Server

#### Prerequisites

- SQL Server
- [Visual Studio 2017 version 15.3 with .NET Core SDK 2.0](https://www.microsoft.com/net/core/)

#### Steps to run

- Create a database in SQL Server
- Update the connection string in appsettings.json in SimplCommerce.WebHost
- Build whole solution.
- In the Task Runner Explorer, right click on the "copy-modules" task and Run.
- Open Package Manager Console Window and type "Update-Database" then press "Enter". This action will create database schema.
- Execute src/Database/StaticData.sql on the created database to insert seed data.
- In Visual Studio, press "Control + F5".
- The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!

## Mac/Linux with PostgreSQL

#### Prerequisite

- PostgreSQL
- NodeJS
- [.NET Core SDK 2.0](https://www.microsoft.com/net/core/)

#### Steps to run

- Create a database in PostgreSQL.
- Update the connection string in appsettings.json in SimplCommerce.WebHost.
- Run file "sudo ./simpl-build.sh".
- Execute src/Database/StaticData_Postgres.sql on the created database to insert seed data.
- In the terminal, navigate to the "src/SimplCommerce.WebHost" type "dotnet run" and hit "Enter".
- Open browser, open http://localhost:5000. The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!