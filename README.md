# tagliatelle-action

### GitHub action for [xlyk/tagliatelle](https://github.com/xlyk/tagliatelle)

Utility to update tags and version numbers in project files. Useful for config files, kustomize projects, and helm
charts.

## Inputs

| Input       | Required | Description                                                      |
|-------------|----------|------------------------------------------------------------------|
| user        | yes      | github username                                                  |
| token       | yes      | github personal access token                                     |
| repo        | yes      | repo that contains target file (access and permissions required) |
| file        | yes      | target file to update                                            |
| tag         | yes      | string to use as replacement                                     |
| pattern     | yes      | regex pattern to use                                             |
| pattern     | yes      | regex pattern to use                                             |
| project     | yes      | name of the project                                              |
| environment | yes      | name of the environment                                          |

## Example usage

```yaml
uses: xlyk/tagliatelle@v2
with:
  user: 'your-username'
  token: "${{ secrets.GH_ACTIONS_ACCESS_TOKEN }}"
  repo: 'https://github.com/xlyk/tagliatelle.git'
  file: 'sample.yaml'
  project: tagliatelle
  environment: prod
  tag: '3.1.4'
  pattern: >
    (?mi)(newTag: ["']?)(\d+\.\d+\.\d+)(["']?)$```

