# Library App

The Library App is a .NET console application for managing library patrons and book loans. Its code is divided into application-core, infrastructure, and console projects, with unit tests for the core services.

## Project structure

```text
AccelerateDevGHCopilot/
├── src/
│   ├── Library.ApplicationCore/   # Domain entities, interfaces, enums, and services
│   ├── Library.Console/           # Console UI, startup, configuration, and JSON data
│   │   └── Json/                  # Authors, books, book items, loans, and patrons
│   └── Library.Infrastructure/    # JSON data loading and repository implementations
└── tests/
    └── UnitTests/                 # xUnit tests for application-core services
```

`Library.Console/appSettings.json` configures the paths to the JSON data files. The console project loads the data and uses the repositories and application services to handle library operations.

## Requirements

- .NET 9 SDK

## Usage

Run these commands from the `AccelerateDevGHCopilot` directory:

```sh
dotnet build src/Library.Console/Library.Console.csproj
dotnet run --project src/Library.Console/Library.Console.csproj
dotnet test tests/UnitTests/UnitTests.csproj
```

The console app is interactive. Follow its prompts to search for patrons, view loans, and perform available loan actions.

## License

This project is distributed under the MIT License. See the repository's [LICENSE](../../../LICENSE) file for the license text.
