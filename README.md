# DepsMissingExample

Minimal repo to reproduce issue desribed here:
https://github.com/dotnet/sdk/issues/29974

To reproduce, go to ProjectB directory directly.
Write dotnet publish

Examine output:
ProjectA.deps.json will be missing

In this small example, ProjectA will still run as it doesn't have any real dependencies, in real world application, it will fail to load.

Workaround:
Remove from ProjectA's csproj:

    <PackageReference Include="NSwag.MSBuild" Version="13.18.2">
      <PrivateAssets>all</PrivateAssets>
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
    </PackageReference>

to

    <PackageReference Include="NSwag.MSBuild" Version="13.18.2">
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
    </PackageReference>

