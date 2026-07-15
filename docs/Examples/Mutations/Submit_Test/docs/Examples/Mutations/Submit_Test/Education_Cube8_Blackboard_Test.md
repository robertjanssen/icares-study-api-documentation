# Education Cube8 Blackboard Test

## Purpose

Submits the completed answer for an **Education Cube8 Blackboard Test**.

The answer contains the question identifier and the selected combination of values.

---

## GraphQL Request

```graphql
mutation submitEducationCube8BlackboardTestAnswer
(
  $id           : Int!,
  $answers      : [SubmitTestAnswerInput!]!,
  $with_language: Boolean
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
    result_url
    secret
    secret_url(with_language: $with_language)
  }
}
```

---

## Query Variables

Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation for an `education_cube8_blackboard_test`.

```json
{
  "id": << test id >>,
  "answers": [
    {
      "id": 938,
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
- Question identifier `938` is specific to the **Education Cube8 Blackboard Test**.
- The `value` contains the selected answer codes combined into one string.
- Use the available answer values from the corresponding test form when constructing this value.
- Other study tests use different question identifiers and answer structures.

---

## Related Examples

Previous steps:

- **Mutations → Invite → Invite Study Test**
- **Queries → Forms → Education Cube8 Blackboard Test**

Next step:

- **Queries → Results**
