
# Template for ASP .Net Core Web API

Template for ASP .Net Core Web API project, including:

- OpenTelemetry logs and traces
- Swagger documentation
- Data Type Object
- ...

Based on Microsoft documentation: https://learn.microsoft.com/en-us/dotnet/core/tools/custom-templates

## Create a Nuget package

```bash
# Define the output directory, where the Nuget package will be produced
OUTPUT_DIRECTORY=./NugetPackages
# Create the directory
mkdir -p $OUTPUT_DIRECTORY
# Generate the package
dotnet pack MyDotnetTemplates.csproj -o ${OUTPUT_DIRECTORY}
```

## Install a template package

See : https://learn.microsoft.com/en-us/dotnet/core/tools/custom-templates

```bash
# Package ID
PACKAGE_ID=Galamome.Utility.Templates
# Package version, comming from 'PackageVersion' of the CSPROJ
PACKAGE_VERSION=1.0.2
dotnet new --install ${OUTPUT_DIRECTORY}/${PACKAGE_ID}.${PACKAGE_VERSION}.nupkg
```

## Create a new instance from the template

The template package shall have been installed first.

Options:
- `-n`: the name of the new project to be created (will replace any `sourceName` value as defined in `template.json`)
- `-o`: folder

```bash
dotnet new galamomewebapi -n MyApi -o MyApi
```

> NOTICE: the short name (`galamomewebapi`) of the template comes from `templates/webapi/.template.config/template.json`, property `shortname`.

