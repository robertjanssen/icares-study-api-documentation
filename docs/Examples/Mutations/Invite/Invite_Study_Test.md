[Documentation](../../../README.md) > [Examples](../../README.md) > [Mutations](../README.md) > **Invite**
# Invite Study Test

## Purpose

Creates one or more **study tests**.

The response contains all information required to start the study test, including the generated test secret and the URL that can be used to open the test.

---

## GraphQL Request

Copy and paste the following GraphQL mutation into the **Query / Mutation editor** of the GraphiQL in-browser tool.

```graphql
mutation Invite
(
  $test:          String!,
  $amount:        Int!,
  $readable:      Boolean,
  $with_language: Boolean
)
{
  invite(test: $test, amount: $amount, readable: $readable)
  {
    id
    type
    {
      type
      name
    }
    created_at
    started_at
    finished_at
    result_url
    secret
    secret_url(with_language: $with_language)
  }
}
```

---

## Query Variables

Copy and paste the following JSON into the **Query Variables** window of the GraphiQL in-browser tool.

```json
{
  "test":          "education_choice_test",
  "amount":        1,
  "readable":      true,
  "with_language": true
}
```

---

## Response

The response may contain the following information:

| Field | Description |
|------|-------------|
| `id` | Unique identifier of the created study test. |
| `type` | Technical and display name of the study test. |
| `created_at` | Date and time the study test was created. |
| `started_at` | Date and time the participant started the test (if applicable). |
| `finished_at` | Date and time the participant completed the test (if applicable). |
| `result_url` | URL to the study test results (available after completion). |
| `secret` | Unique test secret used to identify the study test. |
| `secret_url()` | URL that opens the study test for the participant. |

Only the fields requested in the GraphQL mutation are returned.

---

## Available Study Tests

The `test` Query Variable accepts one of the following values.

| Value | Study Test |
|------|------------|
| `education_choice_test` | Education Choice Test |
| `education_cube8_photo_test` | Education Cube8 Photo Test |
| `education_cube8_blackboard_test` | Education Cube8 Blackboard Test |
| `education_cube8_notice_board_test` | Education Cube8 Notice Board Test |
| `study_swiper_test` | Study Swiper Test |

---

## Typical Workflow

1. Execute the **Invite** mutation.
2. Store the returned **secret**.
3. Open the returned **secret_url** or provide it to the participant.
4. Retrieve the corresponding study test form.
5. Submit the completed answers.
6. Retrieve the calculated study results.

---

## Notes

- The GraphQL response only contains the fields explicitly requested.
- Set `amount` to the number of study tests that should be created.
- Setting `readable` to `true` returns user-friendly URLs where applicable.
- Setting `with_language` to `true` includes the configured language in the generated test URL.
