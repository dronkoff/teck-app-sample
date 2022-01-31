FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /App
COPY . ./
RUN dotnet build
RUN dotnet publish -c Release -o out
RUN ls

FROM mcr.microsoft.com/dotnet/runtime:6.0
WORKDIR /App
COPY --from=build /App/out ./
ENTRYPOINT ["dotnet", "TestApp.Docker.dll", "10"]