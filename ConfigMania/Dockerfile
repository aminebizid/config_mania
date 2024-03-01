FROM mcr.microsoft.com/dotnet/runtime:7.0 AS base
WORKDIR /app

FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["ConfigMania/ConfigMania.csproj", "ConfigMania/"]
RUN dotnet restore "ConfigMania/ConfigMania.csproj"
COPY . .
WORKDIR "/src/ConfigMania"
RUN dotnet build "ConfigMania.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "ConfigMania.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "ConfigMania.dll"]
