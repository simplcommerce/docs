# Getting Started

---

## Docker
- First run the database: `docker run --name simpldb -d postgres`
- Then run the app: `docker run --name simplsite -d -p 5000:80 --link simpldb:simpldb simplcommerce/nightly-build`

## Visual Studio 2017 and SQL Server

#### Prerequisites

- SQL Server
- [Visual Studio 2017 version 15.7 with .NET Core SDK 2.1](https://www.microsoft.com/net/download/all)

#### Steps to run

- Update the connection string in appsettings.json in SimplCommerce.WebHost
- Build whole solution.
- Open Package Manager Console Window and type "Update-Database" then press "Enter". This action will create database schema.
- In Visual Studio, press "Control + F5".
- The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!

## Mac/Linux with PostgreSQL

#### Prerequisite

- PostgreSQL
- NodeJS
- [.NET Core SDK 2.1](https://www.microsoft.com/net/download/all)

#### Steps to run

- Update the connection string in appsettings.json in SimplCommerce.WebHost.
- Run file "sudo ./simpl-build.sh".
- In the terminal, navigate to the "src/SimplCommerce.WebHost" type "dotnet run" and hit "Enter".
- Open browser, open http://localhost:5000. The back-office can access via /Admin using the pre-created account: admin@simplcommerce.com, 1qazZAQ!
