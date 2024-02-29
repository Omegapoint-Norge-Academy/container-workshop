# Oppgave 7

Lag en flerstegs Dockerfile som bygger og kjører .NET-applikasjonen i `App`.

Benytt `mcr.microsoft.com/dotnet/sdk:8.0` som base image for bygg-steget, og `mcr.microsoft.com/dotnet/aspnet:8.0`for kjøre-steget.

<details>
<summary>Hint 1</summary>
Prosjektet bygges med 

```
dotnet publish -c release -o out
```
</details>

<details>
<summary>Hint 2</summary>

```
FROM baseimg AS base

[...]
FROM runtime
COPY --from=base /App/out .
```
</details>

<details>
<summary>Løsning</summary>

```
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build-env
WORKDIR /App

# Copy everything
COPY . ./
# Restore as distinct layers
RUN dotnet restore
# Build and publish a release
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /App
COPY --from=build-env /App/out .
ENTRYPOINT ["dotnet", "DotNet.Docker.dll"]
```
</details>
