# I8Beef.CodeAnalysis.EditorConfig
Personal Code Analysis editorconfig

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

Install the package I8Beef.CodeAnalysis.EditorConfig to each project in the target solution. The first time it is installed it will copy the editorconfig to the project.