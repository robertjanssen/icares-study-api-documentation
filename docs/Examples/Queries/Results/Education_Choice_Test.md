[Documentation](../../../README.md) > [Examples](../../README.md) > [Queries](../README.md) > **Results**
# Education Choice Test Results

## Purpose

Retrieves the study advice for a completed **Education Choice Test**.

The returned results can optionally be filtered by country, education level, educational institution and language.

---

## GraphQL Request

```graphql
query getEducationChoiceTestResult
(
  $id:                         Int!,
  $country_id:                 Int,
  $education_level_id:         Int,
  $educational_institution_id: Int,
  $language_id:                Int,
  $results_limit:              Int
)
{
  education_choice_test(id: $id)
  {
    test
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
    educations(
      country:                 $country_id,
      level:                   $education_level_id,
      language:                $language_id,
      educational_institution: $educational_institution_id,
      limit:                   $results_limit
    )
    {
      country
      {
        id
        name
        code
      }
      level
      {
        id
        name
        country
        {
          id
          name
          code
        }
      }
      language
      {
        id
        name
        code
      }
      educational_institution
      {
        id
      }
      total
      nodes
      {
        education
        {
          id
          name
        }
        score
        index
      }
    }
  }
}
```

---

## Query Variables

Replace `<< test id >>` with the identifier of the completed study test and the `<< EDUCATIONAL_INSTITUTION_ID >>` with the id provided in the 1Password Secure Note with the API_TOKEN.

```json
{
  "id":                         << test id >>,
  "country_id":                 158,
  "education_level_id":         5,
  "educational_institution_id": << EDUCATIONAL_INSTITUTION_ID >>,
  "language_id":                20,
  "results_limit":              10
}
```
Typial values for the Netherlands:

| Query Variable | id | Description |
|------|------------|------------|
| `country_id` | 158 | The Netherlands |
| `education_level_id` | 1 | MBO 1 |
| | 2 | MBO 2 |
| | 3 | MBO 3 |
| | 4 | MBO 4 |
| | 663 | MHBO |
| | 5 | HBO Bachelor |
| | 6 | HBO Master |
| | 20 | HBO Associate Degree |
| | 424 | Post-HBO |
| | 7 | WO Bachelor |
| | 8 | WO Master |
| | 758 | Post academisch |
| `language_id` | 20 | Dutch |

Typical values for England:

| Query Variable | id | Description |
|------|------------|------------|
| `country_id` | 252 | England |
| `education_level_id` | 58 | Intermediate level 5 |
| | 59 | Honours level 6 |
| | 60 | Masters level 7 |
| | 61 | Doctoral level 8 |
| | 203 | Certificate level 4 |
| `language_id` | 10 | English |

---

## Response

A successful request returns:

- General information about the completed study test.
- Matching education programmes.
- The calculated score and ranking for each education.
- Information about the selected country, education level, language and educational institution.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- Replace `<< test id >>` with the identifier of the completed study test.
- All filter variables except `id` are optional.
- Set an optional filter to `null` if it is not required.
- Use `results_limit` to limit the number of returned education programmes.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples
⬅️ [Submit Test Answers](../../Mutations/Submit_Test/README.md)
