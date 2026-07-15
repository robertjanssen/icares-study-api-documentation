# Education Choice Test

## Purpose

Submits the completed answers for an **Education Choice Test**.

Each submitted answer consists of a question identifier (`id`) and the selected answer (`value`).

---

## GraphQL Request

Copy and paste the following GraphQL mutation into the **Query / Mutation editor** of the GraphiQL in-browser tool.

```graphql
mutation submitEducationChoiceTestAnswer
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

Copy and paste the following JSON into the **Query Variables** window of the GraphiQL in-browser tool.

Replace **`<< test id >>`** with the identifier returned by the **Invite Study Test** mutation.

```json
{
  "id": << test id >>,
  "answers": [
    { "id": 522, "value": "1" },
    { "id": 523, "value": "2" },
    { "id": 524, "value": "3" },
    { "id": 525, "value": "4" },
    { "id": 526, "value": "1" },
    { "id": 527, "value": "2" },
    { "id": 528, "value": "3" },
    { "id": 529, "value": "4" },
    { "id": 530, "value": "1" },
    { "id": 531, "value": "2" },
    { "id": 532, "value": "3" },
    { "id": 533, "value": "4" },
    { "id": 534, "value": "1" },
    { "id": 535, "value": "2" },
    { "id": 536, "value": "3" },
    { "id": 537, "value": "4" },
    { "id": 538, "value": "1" },
    { "id": 539, "value": "2" },
    { "id": 540, "value": "3" },
    { "id": 541, "value": "4" },
    { "id": 542, "value": "1" },
    { "id": 543, "value": "2" },
    { "id": 544, "value": "3" },
    { "id": 545, "value": "4" },
    { "id": 546, "value": "1" },
    { "id": 547, "value": "2" },
    { "id": 548, "value": "3" },
    { "id": 549, "value": "4" },
    { "id": 550, "value": "1" },
    { "id": 551, "value": "2" },
    { "id": 552, "value": "3" },
    { "id": 553, "value": "4" },
    { "id": 554, "value": "1" },
    { "id": 555, "value": "2" },
    { "id": 556, "value": "3" },
    { "id": 557, "value": "4" },
    { "id": 558, "value": "1" },
    { "id": 559, "value": "2" },
    { "id": 560, "value": "3" },
    { "id": 561, "value": "4" },
    { "id": 562, "value": "1" },
    { "id": 563, "value": "2" },
    { "id": 564, "value": "3" },
    { "id": 565, "value": "4" },
    { "id": 566, "value": "1" },
    { "id": 567, "value": "2" },
    { "id": 568, "value": "3" },
    { "id": 569, "value": "4" },
    { "id": 570, "value": "1" },
    { "id": 571, "value": "2" },
    { "id": 572, "value": "3" },
    { "id": 573, "value": "4" },
    { "id": 574, "value": "1" },
    { "id": 575, "value": "2" },
    { "id": 576, "value": "3" }
  ],
  "with_language": true
}
```

---

## Response

A successful request returns the updated study test.

Typical response fields include:

- Study test identifier
- Study test type
- Creation date
- Start date
- Completion date
- Result URL
- Test secret
- Study test URL

Only the fields requested in the GraphQL mutation are returned.

---

## Notes

- Replace **`<< test id >>`** with the identifier returned by the **Invite Study Test** mutation.
- The question identifiers (`id`) shown in this example are specific to the **Education Choice Test**.
- The available answer values are also specific to this study test.
- Other study tests use different question identifiers and may use different answer values.

---

## Related Examples

Previous step:

- **Mutations → Invite → Invite Study Test**

Next step:

- **Queries → Results**
