[Documentation](../../../README.md) > [Examples](../../README.md) > [Queries](../README.md) > **Forms**
# Education Cube8 Photo Test Form

## Purpose

Retrieves the complete form definition for the **Education Cube8 Photo Test**.

Retrieves the complete form definition for the test type, questions and the available answer options, including the associated images.

---

## GraphQL Request

```graphql
query getEducationCube8PhotoTestForm
{
  education_cube8_photo_test_form
  {
    test_type
    {
      type
      name
    }
    has_genders
    questions
    {
      id
      value
      question
      help
      answers
      {
        value
        gender
        image_url
        title
      }
    }
  }
}
```

---

## Query Variables

This query does not require Query Variables.

---

## Response

A successful request returns the complete form definition for the Education Cube8 Photo Test.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- The `questions` section contains the question identifiers required when submitting the completed test.
- Each question contains its own collection of available answer options.
- The `image_url` field contains the image associated with each answer option.
- The `has_genders` field indicates whether gender-specific answer options are available.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples

---
⬅️ [Invite Study Test](../../Mutations/Invite/Invite_Study_Test.md) |
➡️ [Submit Cube8 Photo Test Answers](../../Mutations/Submit_Test/Education_Cube8_Photo_Test.md)
