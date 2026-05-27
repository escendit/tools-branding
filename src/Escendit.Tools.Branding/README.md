# Escendit.Tools.Branding

A development-only NuGet package that automatically applies standard MSBuild branding properties
and injects shared `LICENSE` and `packageIcon.png` assets into every consuming project at build time.

## Installation

```shell
PM> Install-Package Escendit.Tools.Branding
```

## What It Does

Once installed, the following MSBuild properties are set on your project automatically:

| Property | Default value |
|---|---|
| `Authors` | `Escendit` |
| `Copyright` | `Copyright © Escendit GmbH` |
| `PackageIcon` | `packageIcon.png` |
| `PackageLicenseFile` | `LICENSE` |
| `PackageReadmeFile` | `README.md` |

The shared `LICENSE` and `packageIcon.png` files are also injected into your package automatically
— no manual `<ItemGroup>` entries needed.

## Overriding Defaults

Override any property in your `.csproj` or `.vbproj` after the package is imported:

```xml
<PropertyGroup>
    <Authors>John Doe;Jane Smith</Authors>
    <Copyright>Copyright © My Company</Copyright>
</PropertyGroup>
```

## Notes

- **Development dependency** — produces no runtime output; does not appear as a package dependency.
- Supports single-targeting (`build/`), multi-targeting (`buildMultiTargeting/`), and transitive
  propagation (`buildTransitive/`).

## License

Licensed under the Apache License 2.0.
