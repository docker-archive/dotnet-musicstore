MusicStore (Sample ASP.NET Core application)
============================================

This is a fork of the original [ASP.NET MusicStore sample](https://github.com/aspnet/MusicStore), with some simplification. The CI build artifacts have been removed and the .NET dependencies pinned to a specific version. 

This project is part of ASP.NET Core. You can find samples, documentation and getting started instructions for ASP.NET Core at the [Home](https://github.com/aspnet/home) repo.

## Run the application:
* If you have Visual Studio 2017
	1. Open MusicStore.sln in Visual Studio 2017 and run the individual applications on `IIS Express`.

* If you don't have Visual Studio 2017
	1. Open a command prompt and execute `cd \src\MusicStore\`.
	2. Execute `dotnet restore`.

**NOTE:** App and tests require Visual Studio 2017 LocalDB on the machine to run.
**NOTE:** Since SQL Server is not generlly available on Mac, the InMemoryStore is used to run the application. So the changes that you make will not be persisted.

## Run on Docker Windows Containers

 * [Install Docker for Windows](https://docs.docker.com/docker-for-windows/) or [setup up Docker Windows containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/containers_welcome)
 * `docker-compose -f .\docker-compose.windows.yml build`
 * `docker-compose -f .\docker-compose.windows.yml up`
 * Access MusicStore on either the Windows VM IP or (if container is running locally) on the container IP: `docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" musicstore_web_1`
