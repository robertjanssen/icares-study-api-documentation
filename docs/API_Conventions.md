# API Conventions

This document describes the general conventions used throughout the Icares Study API.

---

# Endpoint

All GraphQL requests are sent using HTTP **POST** to the following endpoint:

```
https://platform.icares.com/graphql
```

---

# Authentication

Access to the API is secured using a unique **API Token**.

The API Token must be included in the HTTP `Authorization` header using the following format:

```http
Authorization: Bearer <API_TOKEN>
```

API Tokens are distributed securely through a **1Password Secure Note**.

Keep your API Token confidential, as it provides access to the API on behalf of your application.

---

# HTTP Headers

Every GraphQL request must include the following HTTP headers.

| Header | Value |
| ------ | ----- |
| `Content-Type` | `application/json` |
| `Authorization` | `Bearer <API_TOKEN>` |

---

# HTTP Method

All GraphQL operations use the HTTP **POST** method.

---

# Request Body

The request body consists of a JSON object containing:

- the GraphQL request;
- optional Query Variables.

Example:

```json
{
  "query": "...",
  "variables": {
  }
}
```

---

# Query Variables

Whenever possible, values should be supplied through **Query Variables** rather than hardcoded into the GraphQL request.

This improves readability and allows the same GraphQL request to be reused with different input values.

---

# Response

The API returns a JSON response.

GraphQL returns **only the fields explicitly requested** in the GraphQL request.

This allows applications to retrieve exactly the information they require and minimizes unnecessary data transfer.

---

# GraphiQL In-Browser Tool

The GraphiQL in-browser tool provides a convenient environment for developing and testing GraphQL requests.

It includes a built-in **Documentation Explorer** that always reflects the current GraphQL schema.

## GraphQL Schema

The GraphiQL in-browser tool automatically exposes all fields that are available in the GraphQL schema.

The examples in this documentation focus on the fields that are commonly used when integrating with the Icares Study API. Depending on your use case, additional fields may be available through the GraphQL schema.

---

# Error Handling

When a request cannot be completed, the response contains one or more GraphQL errors describing the problem.

Typical causes include:

- invalid authentication;
- invalid GraphQL syntax;
- missing required variables;
- invalid variable values;
- insufficient permissions.

Always verify the returned error message before retrying the request.
