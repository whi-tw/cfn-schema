# CFN Schema

This repository provides up-to-date AWS CloudFormation JSON schemas for use in IDEs and other development tools.

## Overview

AWS CloudFormation schemas allow for validation, autocompletion, and documentation of CloudFormation templates in supporting IDEs. This repository automatically fetches the latest CloudFormation template schemas from the official AWS repository and makes them available in an easily consumable format.

## How It Works

- An automated GitHub Actions workflow runs every 8 hours to check for schema updates
- The workflow pulls the latest schemas from the [AWS CloudFormation Template Schema](https://github.com/aws-cloudformation/aws-cloudformation-template-schema) repository
- Updated schemas are stored in the `schema/` directory and committed to this repository
- When changes are detected, a pull request is automatically created

## Using the Schemas

### In VS Code

1. Install the [CloudFormation Linter](https://marketplace.visualstudio.com/items?itemName=kddejong.vscode-cfn-lint) extension
2. Configure the extension to use these schemas:

```json
{
  "cfnlint.schema": {
    "cloudformation": "https://raw.githubusercontent.com/whi-tw/cfn-schema/main/schema/base.schema.json"
  }
}
```

### In Other IDEs

Most IDEs with JSON schema support can be configured to use these schemas. Point your IDE to:

```
https://raw.githubusercontent.com/whi-tw/cfn-schema/main/schema/base.schema.json
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This repository is provided as-is with no explicit license. The AWS CloudFormation Template Schema is governed by its own licensing terms.

## Acknowledgments

This repository is powered by the following projects:

- [AWS CloudFormation Template Schema](https://github.com/aws-cloudformation/aws-cloudformation-template-schema)
- [vscode-cfn-lint](https://github.com/aws-cloudformation/cfn-lint-visual-studio-code) - The GitHub Actions workflow for schema generation was adapted from this project
