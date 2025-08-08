# NuGet Package: Escendit.Tools.Branding
A NuGet package that sets the MSBuild properties such as Authors,
PackageIcon, PackageLicenseFile, PackageReadmeFile, Copyright,
and puts assets for Package Icon, License, and Readme files.

## Installation
To install this package, use the NuGet Package Manager Console:

```shell
PM> Install-Package Escendit.Tools.Branding
```
Or you can search for "Escendit.Tools.Branding" in the NuGet Package Manager UI and install it from there.

## Usage
After installing the package, the MSBuild properties will be set automatically.
You can modify the properties by updating the values in your .csproj or .vbproj file.

For example, to set the Authors property, add the following to your .csproj or .vbproj file:

```xml
<PropertyGroup>
    <Authors>John Doe;Jane Smith</Authors>
</PropertyGroup>
```

## MSBuild Properties
This package sets the following MSBuild properties:

- Authors
- PackageIcon
- PackageLicenseFile
- PackageReadmeFile
- Copyright

You can modify these properties by updating your .csproj or .vbproj file as described in the Usage section.

## Assets
This package includes the following assets:

- PackageIcon: `assets/packageIcon.png`
- License: `assets/LICENSE`
- Readme file: `README.md`

To access the assets, use the relative paths shown above.

## Contributing
If you find a bug or have a feature request, please create an issue in the GitHub repository.

To contribute code, fork the repository and submit a pull request.
Please ensure that your code follows the project's coding standards and is thoroughly tested.

## License
Licensed under Apache License 2.0. See the LICENSE file for the complete license text.
