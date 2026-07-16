[Documentation](../../../README.md) > [Examples](../../README.md) > [Mutations](../README.md) > **Invite**
# Invite Study Test

## Purpose

Creates one or more **study tests**.

The returned `id` uniquely identifies the study test and is required for subsequent API requests.

---

## GraphQL Request

Copy and paste the following GraphQL mutation into the **Query / Mutation editor** of the GraphiQL in-browser tool.

```graphql
mutation Invite
(
  $test:          String!,
  $amount:        Int!
)
{
  invite(test: $test, amount: $amount)
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
  }
}
```

---

## Query Variables

Copy and paste the following JSON into the **Query Variables** window of the GraphiQL in-browser tool.

```json
{
  "test":          "education_choice_test",
  "amount":        1
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
2. Store the returned **id**.
3. Retrieve the corresponding study test form.
4. Submit the completed answers.
5. Retrieve the calculated study results.

---

## Notes

- The GraphQL response only contains the fields explicitly requested.
- Set `amount` to the number of study tests that should be created.
