FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src

COPY ["PitsLanches.csproj", "./"]
RUN dotnet restore "./PitsLanches.csproj"

COPY . .
WORKDIR "/src/."

RUN dotnet publish "PitsLanches.csproj" -c Release -o /app/publish

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS final
WORKDIR /app
COPY --from=build /app/publish .

EXPOSE 8080
ENTRYPOINT ["dotnet", "PitsLanches.dll"]
