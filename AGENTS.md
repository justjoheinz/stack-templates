# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains Stack templates for Haskell projects. These templates are opinionated setups with various default extensions inspired by best practices. The templates are:

1. `base.hsfiles` - Basic Haskell project template using RIO prelude
2. `std.hsfiles` - Standard Haskell project template with comprehensive language extensions
3. `lambda.hsfiles` - AWS Lambda function template for Haskell

## Common Development Commands

### Testing Templates

To test a template locally:

```sh
stack new test-project /absolute/path/to/template.hsfiles
```

For example:

```sh
stack new myproject /Users/markusklink/Projects/haskell/stack-templates/base.hsfiles
```

### Using Published Templates

After publishing to a GitHub account (e.g., justjoheinz), templates can be used with:

```sh
stack new packagename justjoheinz/base
stack new packagename justjoheinz/std
stack new packagename justjoheinz/lambda
```

## Architecture

### Template Structure

All templates follow a similar structure, providing:

- `package.yaml` - Package configuration with dependencies and extensions
- Basic source directories (`src/`, `app/`, `test/`)
- Setup files (`.gitignore`, `LICENSE`, etc.)
- Default test setup using DocTest

### Template-Specific Features

#### Base Template
- Uses RIO prelude (`NoImplicitPrelude`)
- Focuses on practical extensions for everyday development
- Sets up basic testing with DocTest

#### Standard Template
- More comprehensive set of language extensions
- Uses standard Prelude
- Text-based utilities

#### Lambda Template
- Configured for AWS Lambda deployment
- Includes Dockerfile for building deployment package
- Uses aws-lambda-haskell-runtime
- Provides Makefile for building Docker image

## Template Modification Guidelines

When modifying templates:
1. Keep the mustache variables consistent (`{{name}}`, `{{github-username}}`, etc.)
2. Maintain the `{-# START_FILE filename #-}` format
3. Test changes by creating a new project with the template
4. Be careful with language pragmas and extensions - they define the character of each template

Remember that these templates represent opinionated setups, and modifications should align with their intended purpose and style.