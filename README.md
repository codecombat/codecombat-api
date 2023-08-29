# CodeCombat API

Tagging a release on this repository will update the following repos:

- [Node.js SDK](https://github.com/codecombat/codecombat-node)
- [Python SDK](https://github.com/codecombat/codecombat-python)
- [Java SDK](https://github.com/codecombat/codecombat-java)
- [Go SDK](https://github.com/codecombat/codecombat-go)
- [OpenAPI spec](https://github.com/codecombat/codecombat-openapi)
- [Postman collection](https://github.com/codecombat/codecombat-postman)

and the CodeCombat [API docs](api-docs.codecombat.com)

## What is in this repository?

This repository contains

- CodeCombat's Fern API Definition in English and Simplified Chinese which lives in the [definition](./fern/) folder
- Generators (see [generators.yml](./fern/english/generators.yml))

## What is in the API Definition?

The API Definition contains information about what endpoints, types, and errors are used in the API. The definition is broken into smaller files such as [clans.yml](fern/api/definition/clans.yml) and [stats.yml](fern/api/definition/stats.yml).

To make sure that the definition is valid, you can use the Fern CLI.

```bash
npm install -g fern-api # Installs CLI
fern check # Checks if the definition is valid
```

## What are generators?

Generators read in your API Definition and output artifacts (e.g. the TypeScript SDK Generator) and are tracked in [generators.yml](./fern/api/generators.yml).

To trigger the generators run:

```bash
fern generate --group external --version <version>
```

The publish command currently runs in a GitHub workflow (see [ci.yml](.github/workflows/ci.yml#L32))
