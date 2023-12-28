# DocFx Setup Action
A GitHub Action to setup [Docfx](https://dotnet.github.io/docfx/), to [build](https://github.com/clFaster/docfx-build-action) technical documentations.

## Usage
Prerequisites:
- .NET SDK 6.0 or higher

### Action
This action will install the latest version of docfx. 
```yaml
- name: Setup DocFx
  uses: clFaster/docfx-setup-action@v1
```

### Example Workflow
A complete example of a workflow that builds Docfx documentation.
```yaml
- name: Checkout
  uses: actions/checkout@v4

- name: Setup .NET Core 8.x
  uses: actions/setup-dotnet@v3
  with:
    dotnet-version: "8.x"

- name: Setup DocFx
  uses: clFaster/docfx-setup-action@v1

- name: Build Documentation
  uses: clFaster/docfx-build-action@v1
  with:
    docfx-file-path: "docs/docfx.json"
```