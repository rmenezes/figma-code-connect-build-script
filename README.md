# figma-code-connect-build-cli

A command-line interface (CLI) tool for building and managing Code Connect (iOS) projects without Swift Package Manager (SPM).

## Features

- Downloads a mirror of the Figma Code Connect repository from rmenezes/code-connect
- Builds the CLI tool and the Swift CLI tool
- Exports the XCFramework, eliminating the need for SPM
- Allows specifying a custom Swift CLI path in the figma.config.json file

## Usage

1. Ensure your figma.config.json file includes the `customSwiftCLIPath` property:

```json
{
    "codeConnect": {
        "include": [
            "MyProject/**",
        ],
        "exclude": [],
        "parser": "swift",
        "importMappings": {
            "SwiftUI": "SwiftUI"
        },
        "customSwiftCLIPath": "./figma-swift"
    }
}
```

2. Run the build script:

```bash
./build_cli.sh /Output/Path/xcframework
```

This will download the Code Connect repository, build the CLI tool, and export the xcframework.
