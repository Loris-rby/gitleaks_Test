# gitleaks_Test
test tools gitleaks


## Install 

# tool

macOS (Homebrew):
```
brew install gitleaks
```
Windows (Scoop): 
```
scoop install gitleaks
```
Docker: 
```
docker pull zricethechef/gitleaks:latest
```


# for automate install pre-commit 

```
pip install pre-commit
```

Create a configuration file named .pre-commit-config.yaml in the root of your Git repository and add the following:

```
repos:
  - repo: https://github.com/gitleaks/gitleaks
    rev: v8.18.2  # Use the latest stable version
    hooks:
      - id: gitleaks
```

Install the hook into your local .git/ directory:

```
pre-commit install
```

## Automate CI/CD Pipeline

If you use GitHub, Gitleaks  Create a file at .github/workflows/gitleaks.yml:


```
name: Gitleaks Scan

on:
  pull_request:
  push:
    branches: [main, master]

jobs:
  scan:
    name: Gitleaks Security Scan
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0 # Important: fetches all history so gitleaks can scan commits

      - name: Run Gitleaks
        uses: gitleaks/gitleaks-action@v2
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```


## Handling False Positives

Sometimes Gitleaks will flag something that looks like a secret but isn't 

create a .gitleaksignore file in the root of your repository : 

```
# .gitleaksignore
# Ignore a specific mock key in unit tests
src/tests/mock_data.json:gitleaks-rule-id:7be89c1...
```

Alternatively, you can add a comment directly in your code above the flagged line to skip it:

```java
// gitleaks:allow
const fake_api_key = "AIzaSyD-mock-key-for-testing";
```
