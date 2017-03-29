# escape=`
FROM microsoft/dotnet:sdk-nanoserver
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

RUN New-Item -Path \MusicStore\samples\MusicStore -Type Directory; `
    New-Item -Path build -Type Directory

WORKDIR MusicStore
COPY samples/MusicStore/MusicStore.csproj samples/MusicStore/MusicStore.csproj
COPY NuGet.config .
COPY version.props .
COPY build/*.props build/
RUN dotnet restore --runtime win10-x64 .\samples\MusicStore

COPY samples samples
RUN dotnet build --framework netcoreapp1.1 --runtime win10-x64 .\samples\MusicStore

EXPOSE 5000
ENV ASPNETCORE_URLS http://0.0.0.0:5000

WORKDIR /MusicStore/samples/MusicStore
CMD dotnet run --framework netcoreapp1.1
