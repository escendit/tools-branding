# NuGet Package: Escendit.Tools.Branding

A development-only NuGet package that automatically applies standard MSBuild branding properties
(`Authors`, `PackageIcon`, `PackageLicenseFile`, `PackageReadmeFile`, `Copyright`) and injects the
shared `LICENSE` and `packageIcon.png` assets into every consuming project at build time.

## Installation

```shell
PM> Install-Package Escendit.Tools.Branding
```

Or search for `Escendit.Tools.Branding` in the NuGet Package Manager UI.

## What It Does

Once installed, the package:

1. **Sets default MSBuild properties** (via `.props`) on all consuming projects:

   | Property | Default value |
   |---|---|
   | `Authors` | `Escendit` |
   | `Copyright` | `Copyright © Escendit GmbH` |
   | `PackageIcon` | `packageIcon.png` |
   | `PackageLicenseFile` | `LICENSE` |
   | `PackageReadmeFile` | `README.md` |

2. **Injects shared assets** (via `.targets`) into every consuming project's package:
   - `LICENSE` — Apache 2.0 license file
   - `packageIcon.png` — organization package icon

Both files are linked invisibly (not shown in Solution Explorer) and packed automatically — no manual `<ItemGroup>` entries needed.

## Overriding Defaults

All properties can be overridden in the consuming project's `.csproj` or `.vbproj`:

```xml
<PropertyGroup>
    <Authors>John Doe;Jane Smith</Authors>
    <Copyright>Copyright © My Company</Copyright>
</PropertyGroup>
```

Properties set before this package's `.props` is imported take lower precedence; properties set
after will override it. Standard MSBuild property precedence applies.

## Scope

This package has `DevelopmentDependency` set to `true`. It produces no runtime output — it is a
build-time-only tool and will not appear as a dependency in the published package.

It supports single-targeting (`build/`), multi-targeting (`buildMultiTargeting/`), and transitive
propagation (`buildTransitive/`), so projects that depend on a project using this package also
receive the branding properties.

## Requirements

- .NET SDK 10.0.x (`global.json` pins `10.0.102`, rolling forward to the latest patch)
- Targets `netstandard2.0` and `netstandard2.1`

## Contributing

If you find a bug or have a feature request, please open an issue in the GitHub repository.

To contribute code, fork the repository and submit a pull request. Ensure your changes follow the
project's coding standards.

## License

Licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for the full text.
