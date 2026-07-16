[Home](../../../README.md) > [Examples](../../README.md) > [Queries](../README.md) > **Forms**
# Education Cube8 Blackboard Test Form

## Purpose

Retrieves the form definition for the **Education Cube8 Blackboard Test**.

Retrieves the complete form definition for the test type, question information and the available answer options.

---

## GraphQL Request

```graphql
query getEducationCube8BlackboardTestForm
{
  education_cube8_blackboard_test_form
  {
    test_type
    {
      type
      name
    }
    has_genders
    question
    {
      id
      question
      help
    }
    answers
    {
      gender
      value
      title
      description
    }
  }
}
```

---

## Query Variables

This query does not require Query Variables.

---

## Response

A successful request returns the requested form information for the Education Cube8 Blackboard Test.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- The `question` section contains the question identifier required when submitting the completed test.
- The `answers` section contains the available answer values together with their title and description.
- The `has_genders` field indicates whether gender-specific answer options are available.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples

Previous step:

- **Mutations → Invite → Invite Study Test**

Next step:

- **Mutations → Submit Test → Education Cube8 Blackboard Test**
