# Infrastructure

This folder is intended for CloudFormation templates used in the workshop.

## Usage

Place your CloudFormation template files (*.yaml or *.json) in this directory.

## Configuration

Remember to update the `contentspec.yaml` file in the root of the project to reference your CloudFormation templates. For example:

```yaml
infrastructure:
  cloudformationTemplates:
    - templateLocation: static/infrastructure/your-template.yaml
      label: Your Template Name
      parameters:
        - templateParameter: YourParameter
          defaultValue: "default-value"
