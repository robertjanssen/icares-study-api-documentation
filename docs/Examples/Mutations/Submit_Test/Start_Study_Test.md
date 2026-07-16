[Documentation](../../../README.md) > [Examples](../../README.md) > [Mutations](../README.md) > **Submit Tests**
# Start Study Test

## Purpose

Marks a study test as started.

This sets the `started_at` timestamp, which can be used to determine when the participant began the test and, together with `finished_at`, to calculate the test duration.

---

## GraphQL Request

```graphql
mutation startTest
(
  $id           : Int!,
  $with_language: Boolean
)
{
  start_test(id: $id)
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

Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation.

```json
{
  "id": << test id >>,
  "with_language": true
}
```

---

## Response

A successful request returns the updated study test, including the `started_at` timestamp.

Only the fields requested in the GraphQL mutation are returned.

---

## Supported Study Tests

The mutation can be used for the following study test types:

- `education_choice_test`
- `education_cube8_photo_test`
- `education_cube8_blackboard_test`
- `education_cube8_notice_board_test`
- `study_swiper_test`

---

## Notes

- Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation.
- Use this mutation when the participant actually starts the test.
- The `started_at` timestamp can be compared with `finished_at` to determine the test duration.
- Calling this mutation is separate from submitting the completed answers.
- The GraphQL response only contains the fields explicitly requested.

---

## Related Examples

Previous step:

- **Mutations → Invite → Invite Study Test**

Next step:

- **Mutations → Submit Test → Select the matching study test example**
