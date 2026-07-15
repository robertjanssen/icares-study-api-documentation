# Icares Study API Quick Start Guide

## 1. Account

We will create an **Educational Manager** account for you.

You will receive an invitation email to activate your account. Once activated, you can sign in at:

https://platform.icares.com

---

## 2. GraphiQL in-browser tool

After signing in, open:

https://platform.icares.com/graphql

The GraphiQL in-browser tool allows you to:

- explore the GraphQL schema;
- browse the available queries and mutations;
- validate and test your GraphQL requests;
- experiment with query variables.

Because GraphQL is self-documenting, the built-in **Docs** panel always contains the latest API documentation.

**We recommend becoming familiar with GraphiQL before integrating with the API.**

---

## 3. Using the API

The GraphQL endpoint is:

`https://platform.icares.com/graphql`

### API Token

Access to the API is secured using a unique **API Token**.

Your API Token will be shared with you through a **1Password Secure Note**, ensuring it can be transferred securely.

Keep this token confidential, as it provides access to the API on behalf of your application.

### HTTP Request

All GraphQL requests are sent as **HTTP POST** requests.

Every request must include the following HTTP headers:

| Header | Value |
| ------ | ----- |
| `Content-Type` | `application/json` |
| `Authorization` | `Bearer <API_TOKEN>` |

The request body must contain a JSON object with:

- the GraphQL `query`;
- optional `variables`.

### Example (HTTP headers)

```http
POST /graphql HTTP/1.1
Content-Type: application/json
Authorization: Bearer <API_TOKEN>
```
