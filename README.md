# Liquibase Init Hub Action
Official GitHub Action to run Liquibase Init Hub in your GitHub Action Workflow. For more information on how init hub works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Init Hub
Command used to complete Hub and Liquibase setup. Requires a "token" available from hub.liquibase.com with a valid user account. Updates the specified liquibase.properties with a valid Hub API Key, and registers the specified changelog file wih Hub, enabling secure monitoring and sharing of local Liquibase activity within an organization.
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/init-hub@v4.17.0
  with:
    # A required one-time-use code to connect your local Liquibase usage to your existing Liquibase Hub user account. Token is available to registered Hub users at https://hub.liquibase.com.
    # string
    # Required
    token: ""

    # Relative or fully qualified path to the changelog file
    # string
    # Optional
    changelogFile: ""

    # Password to use to connect to the database
    # string
    # Optional
    password: ""

    # An optional parameter used to specify the directory containing files (existing or to be auto-created) to be used with Liquibase
    # string
    # Optional
    projectDir: ""

    # The JDBC database connection URL
    # string
    # Optional
    url: ""

    # Username to use to connect to the database
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase init hub action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/init-hub@v4.17.0
    with:
      token: ""
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
