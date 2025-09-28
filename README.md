# Stack Templates

Opinionated templates for Haskell projects with carefully selected language extensions inspired by [An Opinionated Guide to Haskell in 2018](https://lexi-lambda.github.io/blog/2018/02/10/an-opinionated-guide-to-haskell-in-2018/).

## Available Templates

- **base**: Basic Haskell project template using RIO prelude and essential extensions
- **std**: Standard Haskell project template with comprehensive language extensions
- **lambda**: AWS Lambda function template for Haskell with Docker support

All templates use GHC2021 language standard and include configurations for multiple GHC versions.

## Usage

### Creating a new project

```sh
stack new packagename justjoheinz/base
stack new packagename justjoheinz/std
stack new packagename justjoheinz/lambda
```

### Using specific GHC versions

Each template includes configurations for multiple GHC versions:
- `stack-9.8.4.yaml`: Uses GHC 9.8.4 (LTS 23.28)
- `stack-9.6.7.yaml`: Uses GHC 9.6.7 (LTS 22.44)

To use a specific GHC version, use the `--stack-yaml` flag:

```sh
# Build with GHC 9.8.4
stack --stack-yaml=stack-9.8.4.yaml build

# Build with GHC 9.6.7
stack --stack-yaml=stack-9.6.7.yaml build
```

You can also set the `STACK_YAML` environment variable:

```sh
# Set GHC version for the current session
export STACK_YAML=stack-9.6.7.yaml
stack build

# Or for a single command
STACK_YAML=stack-9.8.4.yaml stack build
```
