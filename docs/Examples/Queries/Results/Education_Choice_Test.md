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

Replace `<< test id >>` with the identifier of the completed study test.

```json
{
  "id":                         << test id >>,
  "country_id":                 << $COUNTRY_ID >>,
  "education_level_id":         << $EDUCATION_LEVEL_ID >>,
  "educational_institution_id": << $EDUCATIONAL_INSTITUTION_ID >>,
  "language_id":                << $LANGUAGE_ID >>,
  "results_limit":              10
}
```

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

Previous steps:

- **Mutations → Invite → Invite Study Test**
- **Queries → Forms → Education Choice Test**
- **Mutations → Submit Test → Education Choice Test**
