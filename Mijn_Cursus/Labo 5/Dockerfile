FROM mcr.microsoft.com/dotnet/sdk:8.0
WORKDIR /src
COPY ./greeter-csharp/csharpgreeter.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c release -o /app
WORKDIR /app
CMD ["sleep", "infinity"]
