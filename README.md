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



