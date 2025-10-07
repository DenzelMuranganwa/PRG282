# Superhero Records Manager

A Windows desktop application for maintaining a small superhero catalogue. The WinForms interface supports selecting, adding, updating, and deleting records, while a dedicated data layer handles local text-file persistence.

## Core features

- Browse superhero records in a Windows Forms interface.
- Add and edit each hero's name, age, superpower, and exam score.
- Select a record before editing or deleting it.
- Confirm deletions and refresh the displayed records after changes.
- Keep UI, model, and file-handling responsibilities in separate project areas.

## Technology

![C#](https://img.shields.io/badge/C%23-.NET%20Framework-512BD4?logo=dotnet&logoColor=white)
![UI](https://img.shields.io/badge/UI-Windows%20Forms-0078D4?logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

## Architecture and data flow

```text
Windows Forms (Form1)
        |
        +--> Superhero model
        |
        +--> DataHandler
                +--> local superhero text file
```

`Form1` coordinates user actions and selection state. `SuperheroModel.cs` represents each record, and `DataHandler.cs` reads and writes the local text data. The current implementation is file-based; it does not require a database server.

This was a **team project** completed as module coursework.

## Requirements

- Windows
- Visual Studio or Build Tools for Visual Studio with the .NET Framework 4.7.2 targeting pack

## Build and run

Open **Developer PowerShell for Visual Studio** at the repository root:

```powershell
msbuild ".\GroupPTA_19PM_PRG282Project(602330)(GithubLinkInFolder)\PRG282Project_PTA_19PM\PRG282Project_PTA_19PM.sln" /p:Configuration=Release
```

Run the built Windows Forms application:

```powershell
& ".\GroupPTA_19PM_PRG282Project(602330)(GithubLinkInFolder)\PRG282Project_PTA_19PM\bin\Release\PRG282Project_PTA_19PM.exe"
```

## Development notes

- The application stores records in a local text file. Keep user data files out of public commits.
- The project uses the legacy .NET Framework Windows desktop target and is intended to run on Windows.
- No automated test project is included in the supplied source.

## Roadmap

- Add validation for required fields, numeric ranges, and duplicate records.
- Define a versioned storage format and handle corrupt or missing files clearly.
- Add automated tests for CRUD operations and data-file round trips.
- Consider migrating the UI to a supported modern .NET Windows target.

## License

This team project is available under the MIT License with contributor permission. See [LICENSE](LICENSE).
