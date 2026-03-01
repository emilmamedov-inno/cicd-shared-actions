# cicd-shared-actions

Reusable GitHub Actions for CI/CD pipelines.

## Actions

### setup-node-deps

Sets up Node.js and installs dependencies from lockfile (`npm ci`).

```yaml
- uses: emilmamedov-inno/cicd-shared-actions/setup-node-deps@main
  with:
    node-version: '20'  # optional, default: 20
```

### check-version-exists

Checks if a specific npm package version already exists in the registry.

```yaml
- uses: emilmamedov-inno/cicd-shared-actions/check-version-exists@main
  id: version-check
  with:
    package-name: '@scope/my-package'
    version: '1.0.0'

- run: echo "Exists: ${{ steps.version-check.outputs.exists }}"
```

### create-release

Creates a Git tag (`vX.Y.Z`) and a GitHub Release with auto-generated notes.

```yaml
- uses: emilmamedov-inno/cicd-shared-actions/create-release@main
  with:
    version: '1.0.0'
    github-token: ${{ secrets.GITHUB_TOKEN }}
```

## License

MIT
