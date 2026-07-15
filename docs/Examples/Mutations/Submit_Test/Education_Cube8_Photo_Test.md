# Education Cube8 Photo Test

## Purpose

Submits the completed answers for an **Education Cube8 Photo Test**.

Each submitted answer consists of a question identifier (`id`) and the selected answer (`value`).

---

## GraphQL Request

```graphql
mutation submitEducationCube8PhotoTestAnswer
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

Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation for an `education_cube8_photo_test`.

```json
{
  "id": << test id >>,
  "answers": [
    { "id": 929, "value": "1" },
    { "id": 930, "value": "2" },
    { "id": 931, "value": "3" },
    { "id": 932, "value": "4" },
    { "id": 933, "value": "5" },
    { "id": 934, "value": "4" },
    { "id": 935, "value": "3" },
    { "id": 936, "value": "2" },
    { "id": 937, "value": "ACGIORSV" }
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
- Question identifiers `929` through `937` are specific to the **Education Cube8 Photo Test**.
- Questions `929` through `936` use numeric answer values.
- Question `937` uses a combined answer code containing the selected characteristics.
- Use the question identifiers and answer values from the corresponding test form when constructing the request.
- Other study tests use different question identifiers and answer structures.

---

## Related Examples

Previous steps:

- **Mutations → Invite → Invite Study Test**
- **Queries → Forms → Education Cube8 Photo Test**

Next step:

- **Queries → Results**
