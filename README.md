# dotnet-sonar-dockerless

# Install SonarQube Scanner GitHub Action

This GitHub Action installs the SonarQube scanner with Java in a platform-agnostic way.

## Usage

To use this action, include it in your workflow YAML file. Below is an example of how to configure it:

```yaml
name: SonarQube Scan

on: [push, pull_request]

jobs:
  sonarQubeScan:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Install SonarQube scanner
      uses: nosinovacao/dotnet-sonar-dockerless-action@v1
      with:
        version: '6.2.0' # Optional, default is 6.2.0
        step: 'begin' # Required, default is 'begin'
        sonar-url: 'https://your-sonar-server.com' # Required
        sonar-token: ${{ secrets.SONAR_TOKEN }} # Required
        project-key: 'your-project-key' # Required
        extra-args:  # Optional
```

# Inputs
* `version`: The version of the scanner to be used. Default is `6.2.0`.
* `step`: The step to be used. Default is `begin`.
* `sonar-url`: The URL of the SonarQube server. **Required**.
* `sonar-token`: The token for the SonarQube server. **Required**.
* `project-key`: The project key for the SonarQube server. **Required**.
* `extra-args`: Extra arguments to be used. Optional.

# Author
This action is maintained by NOS Inovação.