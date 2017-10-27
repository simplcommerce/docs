In visual studio, right click on the solution choose add new project. In the Add New Project dialog choose ASP.NET Core Web Application. Naming the module as xxx.Module.yyy, the location should be in src\Modules.

After the project has created. Right click on project name choose Edit xxx.Module.yyy.csproj, then replace all entire the csproj with the content below

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
    <PreserveCompilationContext>false</PreserveCompilationContext>
    <EnableDefaultContentItems>false</EnableDefaultContentItems>
    <OutputType>Library</OutputType>
  </PropertyGroup>

  <ItemGroup>
    <ProjectReference Include="..\..\SimplCommerce.Infrastructure\SimplCommerce.Infrastructure.csproj" />
    <ProjectReference Include="..\SimplCommerce.Module.Core\SimplCommerce.Module.Core.csproj" />
  </ItemGroup>

</Project>
```

Delete 2 files: Program.cs and Startup.cs then add a new file call "module.json" with the following structure

```json
{
  "name": "yyy",
  "fullName": "xxx.Module.yyy",
  "version": "1.0.0"
}
```

Congratulations, your module is ready and you can start adding module code.

## Adding Angular module

In the project folder/wwwroot/admin/ create your angular module. You can copy the existing module then modify it.

Create controllers, views, service for your module.

Register your js files by adding them to the SimplCommerce.Module.Core/Views/HomeAdmin/Index.cshtml

Register your angular module to the SimplCommerce.Module.Core/wwwroot/admin/admin-app.js