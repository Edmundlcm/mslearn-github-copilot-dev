# Library App

## Description

Library App is a .NET console application for managing a library's books, patrons, and loans. It uses a layered design: application-core services contain business logic, infrastructure repositories provide data access, and the console project provides the user interface. The application stores its sample data in JSON files.

## Project Structure

- `src/`
  - `Library.ApplicationCore/`
    - `Entities/` — library domain entities, such as books, patrons, and loans
    - `Enums/` — domain enumerations
    - `Interfaces/` — service and repository contracts
    - `Services/` — application and business logic
  - `Library.Console/`
    - `Json/` — JSON data files used by the application
    - `Program.cs` — dependency-injection setup and application entry point
    - `ConsoleApp.cs` — console user interface
    - `appSettings.json` — JSON data file paths
  - `Library.Infrastructure/`
    - `Data/` — JSON data loading and repository implementations
- `tests/`
  - `UnitTests/`
    - `ApplicationCore/LoanService/` — loan service unit tests
    - `ApplicationCore/PatronService/` — patron service unit tests

## Key Classes and Interfaces

- `ConsoleApp` — presents the console workflow and coordinates user actions.
- `LoanService` and `PatronService` — implement application logic for loans and patrons.
- `ILoanService` and `IPatronService` — define the service operations used by the console application.
- `ILoanRepository` and `IPatronRepository` — define data-access operations for loans and patrons.
- `JsonLoanRepository` and `JsonPatronRepository` — implement repository operations using JSON-backed data.
- `JsonData` — loads and saves JSON data and populates related entities, such as a loan's patron and book item.
- Domain entities include `Author`, `Book`, `BookItem`, `Loan`, and `Patron`.

## Usage

Install the .NET 9 SDK. From this project directory, restore dependencies, run the console application, or run the unit tests:

```shell
dotnet restore
dotnet run --project src/Library.Console
dotnet test tests/UnitTests
```

The JSON file paths are configured in `src/Library.Console/appSettings.json`. The console app expects to be started with this project directory as its working directory.

## License

This project is distributed under the MIT License. See the repository's [LICENSE](../../../LICENSE) file for details.