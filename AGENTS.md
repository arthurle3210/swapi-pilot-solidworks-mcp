# SolidWorks C# Automation Framework

## Architecture

```
AI ─── generate_csharp_project (MCP) ─── .csproj + Program.cs
                                              │
                                         dotnet run ─── SolidWorks
```

**Principle: Always generate C# console projects. Do not use Python or VBA unless the user explicitly requests it.**

## Workflow

1. Use `search_solidworks_api` to find the correct API
2. Use `get_api_detail` to review parameters and example code
3. Use `get_enum` to confirm enum values if needed
4. Use `generate_csharp_project` to create the project with task code
5. Run `dotnet run --project <path>` and report results

## Notes

1. **Search API**: Before writing SolidWorks code, always use `search_solidworks_api` to find the correct API. Never write API calls from memory
2. **Check details**: After finding an API, use `get_api_detail` to review full parameter descriptions and example code
3. **Check enums**: When a parameter requires an enum, use `get_enum` to confirm the correct enum values. Never guess enum member names
4. **Chinese terms**: Supports Chinese search (e.g. searching "薄殼" auto-translates to Shell)
5. **Generate project**: Use `generate_csharp_project` with only the task logic. The template handles SolidWorks connection, COM cleanup, and error handling automatically
6. **Execute immediately after writing**: Run `dotnet run --project <path>` immediately and report results
7. **Project path**: Always generate projects in the current working directory under a `SolidWorksConsole` subfolder
