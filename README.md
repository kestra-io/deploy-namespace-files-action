# Kestra Deploy Namespace Files Action

Official GitHub Action to deploy [Namespace Files](https://kestra.io/docs/concepts/namespace-files) from a folder, as part of your [CI/CD pipeline](https://kestra.io/docs/version-control-cicd/cicd/github-action).

Split out of [`kestra-io/github-actions`](https://github.com/kestra-io/github-actions) so it can be published standalone on the GitHub Marketplace (marketplace requires 1 repo = 1 action).

## Usage

```yaml
- uses: actions/checkout@v4
- uses: kestra-io/deploy-namespace-files-action@main
  with:
    localPath: ./config
    namespace: engineering
    namespacePath: config
    server: ${{ secrets.KESTRA_HOSTNAME }}
```

## Inputs

| Name | Description | Default |
| --- | --- | --- |
| `localPath` | Path to your file or directory containing your files | `./` |
| `namespacePath` | Remote namespace path to deploy your files to | required |
| `namespace` | Namespace to deploy files to | required |
| `override` | Override files if they already exist | `false` |
| `server` | URL of your Kestra server | required |
| `apiToken` | API Token (EE only) | - |
| `user` / `password` | Basic auth credentials | - |
| `tenant` | Tenant identifier (EE only) | `main` |
| `kestractlVersion` | Version of [kestractl](https://github.com/kestra-io/kestractl) to use | `latest` |

## Links
- Docs: https://kestra.io/docs/how-to-guides/github-actions
- Related actions: [`validate-flows-action`](https://github.com/kestra-io/validate-flows-action), [`deploy-flows-action`](https://github.com/kestra-io/deploy-flows-action)
