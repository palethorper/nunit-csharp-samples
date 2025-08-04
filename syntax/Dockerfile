# Use the official .NET 8 SDK image
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /app

# Copy everything (solution and projects)
COPY . ./

# Restore dependencies
RUN dotnet restore

# Build the solution (replace with your .sln file if needed)
RUN dotnet build --no-restore

# Run NUnit tests (replace with your test project .csproj if needed)
RUN dotnet test --no-build --logger:"trx"

# Optionally, you can use a test-specific entrypoint for CI/CD
# ENTRYPOINT ["dotnet", "test", "--logger:trx"]