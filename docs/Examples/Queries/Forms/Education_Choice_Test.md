[Documentation](../../../README.md) > [Examples](../../README.md) > [Queries](../README.md) > **Forms**
# Education Choice Test Form

## Purpose

Retrieves the form definition for the **Education Choice Test**.

Retrieves the complete form definition for the the test type, questions, help texts and available answers.

---

## GraphQL Request

```graphql
query getEducationChoiceTestForm
{
  education_choice_test_form
  {
    test_type
    {
      type
      name
    }
    questions
    {
      id
      question
      help
    }
    answers
    {
      value
      answer
    }
  }
}
```

---

## Query Variables

This query does not require Query Variables.

---

## Response

A successful request returns the requested form information for the Education Choice Test.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- The `questions` section contains the question identifiers required when submitting the completed test.
- The `answers` section contains the available answer values.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples

---
⬅️ [Invite Study Test](../../Mutations/Invite/Invite_Study_Test.md) |
➡️ [Submit Education Choice Test Answers](../Mutations/Submit/Education_Choice_Test.md)
