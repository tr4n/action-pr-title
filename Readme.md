# Pull Request (PR) title naming rules

Github action to enforce Pull Request title conventions

## Inputs

##### `regex` (**Optional**)
Regex to validate the pull request title. Defaults to `.+`.

##### `allowed_prefixes` (**Optional**)
Comma separated list of prefix allowed to be used in title. eg: feature,hotfix,JIRA-. Defaults to `''`.

##### `prefix_case_sensitive` (**Optional**)
Are the allowed prefixes case sensitive?. Defaults to `false`.

##### `min_length` (**Optional**)
Min length of title. Defaults to `1`.

##### `max_length` (**Optional**)
Max length of title. Defaults to `-1`.

## Usage

```yaml
name: 'PR Title Checker'
on: 
  pull_request:
    types: [edited, opened, synchronize, reopened]

jobs:
  title-check:
    runs-on: ubuntu-latest
    steps:
      - uses: naveenk1223/action-pr-title@master
        with:
          regex: '.+' # Regex the title should match.
          allowed_prefixes: 'feature,fix,bugfix,patch,enhancement,hotfix' # title should start with the given prefix
          prefix_case_sensitive: false # title prefix are case insensitive
          min_length: 10 # Min length of the title
          max_length: -1 # Max length of the title
```

## License
The scripts and documentation in this project are released under the [MIT License](./LICENSE)
