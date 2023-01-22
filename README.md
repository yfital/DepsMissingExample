# DepsMissingExample

Minimal repo to reproduce issue desribed here:
https://github.com/dotnet/sdk/issues/29974

To reproduce, go to ProjectB directory directly.
Write dotnet publish

Examine output:
ProjectA.deps.json will be missing

In this small example, ProjectA will still run as it doesn't have any real dependencies, in real world application, it will fail to load.
