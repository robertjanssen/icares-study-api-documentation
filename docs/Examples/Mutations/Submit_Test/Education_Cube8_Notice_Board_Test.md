[Documentation](../../../README.md) > [Examples](../../README.md) > [Mutations](../README.md) > **Submit Tests**
# Education Cube8 Notice Board Test

## Purpose

Submits the completed answer for an **Education Cube8 Notice Board Test**.

The answer contains the question identifier and the selected combination of values.

---

## GraphQL Request

```graphql
mutation submitEducationCube8NoticeBoardTestAnswer
(
  $id           : Int!,
  $answers      : [SubmitTestAnswerInput!]!
)
{
  submit_test(id: $id, answers: $answers)
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

Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation for an `education_cube8_notice_board_test`.

```json
{
  "id": << test id >>,
  "answers": [
    {
      "id": 939,
      "value": "ACGIORSV"
    }
  ],
  "with_language": true
}
```

---

## Response

A successful request returns the updated study test.

Only the fields requested in the GraphQL mutation are returned.

---

## Notes

- Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation.
- Question identifier `939` is specific to the **Education Cube8 Notice Board Test**.
- The `value` contains the selected answer codes combined into one string.
- Use the available answer values from the corresponding test form when constructing this value.
- Other study tests use different question identifiers and answer structures.

---

## Related Examples

Previous steps:

- **Mutations → Invite → Invite Study Test**
- **Queries → Forms → Education Cube8 Notice Board Test**

Next step:

- **Queries → Results**
