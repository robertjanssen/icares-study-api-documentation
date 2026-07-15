# Icares Study API Developer Documentation

Welcome to the official developer documentation for the Icares Study API.

This repository contains everything required to integrate with the Icares Study API, including Quick Start Guides and ready-to-use GraphQL examples.

## Documentation

### Quick Start Guides

If you are integrating with the API for the first time, we recommend starting with the Quick Start Guides.

- [Icares Study API Quick Start Guide](docs/Quick_Start_Guides/Icares_Study_API_Quick_Start_Guide.md).
- [GraphiQL In-Browser Tool Quick Start Guide](docs/Quick_Start_Guides/Icares_Study_API_GraphiQL_in_browser_tool_Quick_Start_Guide.md)

### Example Library

The Example Library contains ready-to-use GraphQL examples that can be copied directly into the GraphiQL in-browser tool or adapted for use in your own application.

Examples are grouped into:

- [Mutations](docs/Examples/Mutations)
- [Queries](docs/Examples/Queries)

## Typical Integration Workflow

A typical integration consists of the following steps:

1. Invite a study test.
2. Retrieve the test form.
3. Start the study test (optional).
4. Submit the completed answers.
5. Retrieve the results.
6. Retrieve shared registrations (optional, for educational institutions).

## Authentication

All API requests use HTTP POST and are authenticated using a Bearer Token.

For more information, see the [**Icares Study API Quick Start Guide**](docs/Quick_Start_Guides/Icares_Study_API_Quick_Start_Guide.md).
