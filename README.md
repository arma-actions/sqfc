# SQFC action

This action compiles SQF files to SQFC on Windows runners

## Example usage

### Config file

Create `sqfc.json` in your repository root.
Adjust paths as needed.

```json
{
  "inputDirs": [
    "P:/"
  ],
  "includePaths": [
    "P:/"
  ],
  "excludeList": [
  ],
  "outputDir": "P:/",
  "workerThreads": 2
}

```

### Github Workflow

Create a GitHub Actions workflow in `.github/workflows`.


```yaml
jobs:
  windows:
    name: Windows

    runs-on: windows-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Create work drive
        run: 'subst P: .'

      - uses: arma-actions/sqfc@latest
        with:
          directory: .
```
