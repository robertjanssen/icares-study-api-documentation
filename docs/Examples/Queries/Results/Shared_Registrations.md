# Shared Registrations

## Purpose

Retrieves registrations for students who have explicitly agreed to share their personal information and study advice with an educational institution.

This query is intended for educational institutions using an Icares Study portal (for example, `https://<educational_institution>.icares.com`).

The response includes the student's personal information together with the completed Education Choice Test and the calculated education recommendations.

---

## GraphQL Request

```graphql
query getSharedRegistrations
(
  $start_date:                 Date!,
  $end_date:                   Date!,
  $with_language:              Boolean,
  $country_id:                 Int,
  $education_level_id:         Int,
  $language_id:                Int,
  $educational_institution_id: Int,
  $results_limit:              Int
)
{
  shared_registrations(start_date: $start_date, end_date: $end_date)
  {
    id
    firstname
    middlename
    lastname
    email
    accepted_share_educ_at
    phone
    zipcode
    country
    {
      id
      name
      code
    }
    nationality
    {
      id
      name
      code
    }
    gender
    birthdate
    language
    {
      id
      name
      code
    }
    education_level
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
    study_year
    education_choice_test
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
        secret
        secret_url(with_language:$with_language)
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
}
```

---

## Query Variables

```json
{
  "start_date":                 "2026-01-01",
  "end_date":                   "2026-07-14",
  "with_language":              true,
  "country_id":                 << $COUNTRY_ID >>,
  "education_level_id":         << $EDUCATION_LEVEL_ID >>,
  "language_id":                << $LANGUAGE_ID >>,
  "educational_institution_id": << $EDUCATIONAL_INSTITUTION_ID >>,
  "results_limit":              3
}
```

---

## Response

A successful request returns:

- Student personal information.
- Contact details.
- Country, language and education level.
- The date on which the student agreed to share their information.
- The completed Education Choice Test.
- Matching education programmes with their calculated scores.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- Only students who have explicitly agreed to share their information are returned.
- `start_date` and `end_date` determine the registration period.
- All filter variables except the date range are optional.
- Set an optional filter to `null` if it is not required.
- Use `results_limit` to limit the number of returned education programmes.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples

Related examples:

- **Queries → Results → Education Choice Test Results**
- **Queries → Forms → Education Choice Test**
- **Mutations → Invite → Invite Study Test**
