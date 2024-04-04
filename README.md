# .NET Build

Uses the .NET CLI `dotnet build` [command](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-build) that builds specified projects or the solution itself including all of its dependencies.

Supports `projects` input we learned to appreciate from [AzDO DotNetCoreCLI](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/dotnet-core-cli-v2?view=azure-pipelines).

> This action is part of the Codebelt ecosystem and ensures a consistent way of: 
> 
> - Defining your CI/CD pipeline 
> - Structuring your repository
> - Keeping your codebase small and feasible
> - Writing clean and maintainable code
> - Deploying your code to different environments
> - Automating as much as possible
>
> A paved path to excel as a DevSecOps Engineer.

## Usage

To use this action in your GitHub repository, you can follow these steps:

```yaml
uses: codebeltnet/dotnet-build@main
```

### Inputs

```yaml
with:
  # Optional path to the project(s) file to restore. Pass empty to have MSBuild use the default behavior.
  # Supports globbing.
  projects: '**/*.csproj'
  # Defines the build configuration.
  configuration: 'Release'
  # Compiles for a specific framework. The framework must be defined in the project file.
  framework: 'net8.0'
  # Sets the verbosity level of the command.
  # Allowed values are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic]. 
  # The default is quiet.
  level: 'quiet'
  # Provides a way to fully customize the build. See https://learn.microsoft.com/en-us/visualstudio/msbuild/msbuild-command-line-reference?view=vs-2022#switches for more information.
  buildSwitches: ''
  # Upload the generated build artifact.
  uploadBuildArtifact: 'true'
```

### Outputs

This action has no outputs.

## Examples

### Build for Release and upload build artifact

```yaml
- name: Build for Release
  uses: codebeltnet/dotnet-build@main
  with:
    configuration: Release
```

### Build for Debug and prevent upload of build artifact

```yaml
- name: Build for Debug
  uses: codebeltnet/dotnet-build@main
  with:
    configuration: Debug
    uploadBuildArtifact: false
```

## Contributing to .NET Build

Contributions are welcome! 
Feel free to submit issues, feature requests, or pull requests to help improve this action.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
