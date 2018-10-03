FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
COPY TestCoreWeb.csproj TestCoreWeb/
RUN dotnet restore TestCoreWeb/TestCoreWeb.csproj
COPY . ./TestCoreWeb
WORKDIR /src/TestCoreWeb
RUN dotnet build TestCoreWeb.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish TestCoreWeb.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "TestCoreWeb.dll"]
