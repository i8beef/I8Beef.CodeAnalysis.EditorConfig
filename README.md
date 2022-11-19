# I8Beef.CodeAnalysis.EditorConfig
Personal Code Analysis editorconfig for .NET 5 and above

# Usage
Make sure the project in question has a nuget.config in the main solution directory that matches the following:

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="MyGet I8Beef" value="https://www.myget.org/F/i8beef/api/v2" />
  </packageSources> 
</configuration>
```

Install the package I8Beef.CodeAnalysis.EditorConfig to each project in the target solution. The first time it is installed it will copy the editorconfig to the project. You should not update this file directly as package reinstalls will overwrite it.

# Explanation
The `I8Beef.CodeAnalysis.EditorConfig.props` file will set various settings in the project file automatically. These include:

1. `<LangVersion>latest</LangVersion>` - Automatically use the most recent version of C# available for compilation, exposing newest features
2. `<GenerateDocumentationFile>true</GenerateDocumentationFile>` - Generate XML documentation files on builds
3. `<EnableNETAnalyzers>true</EnableNETAnalyzers>` - Enable the .NET analyzers from Microsoft.CodeAnalysis.NetAnalyzers overall
4. `<RunAnalyzersDuringBuild>true</RunAnalyzersDuringBuild>` - Evaluate analyzers during build
5. `<RunAnalyzersDuringLiveAnalysis>true</RunAnalyzersDuringLiveAnalysis>` - Evaluate analyzers when live editing in IDE
6. `<TreatWarningsAsErrors>true</TreatWarningsAsErrors>` - Treat warnings as errors for the build generally
7. `<WarningsAsErrors />` - Explicit warnings to treat as errors
8. `<WarningsNotAsErrors />` - Explicit warnings to NOT treat as errors
9. `<EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>` - Enforce code STYLE analyzers during build, not just in IDE
10. `<CodeAnalysisTreatWarningsAsErrors>true</CodeAnalysisTreatWarningsAsErrors>` - Enforce code anaylzer warners as errors actually fail the build
