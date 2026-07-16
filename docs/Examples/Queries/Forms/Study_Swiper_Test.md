[Documentation](../../../README.md) > [Examples](../../README.md) > [Queries](../README.md) > **Forms**
# Study Swiper Test Form

## Purpose

Retrieves the complete form definition for the **Study Swiper Test**.

The response contains the test type, questions and the available answer options.

---

## GraphQL Request

```graphql
query getStudySwiperTestForm
{
  study_swiper_test_form
  {
    test_type
    {
      type
      name
    }
    questions
    {
      id
      image
      question
      help
    }
    answers
    {
      type
      icon
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

A successful request returns the complete form definition for the Study Swiper Test.

Only the fields included in the GraphQL Request are returned.

---

## Notes

- The `questions` section contains the question identifiers required when submitting the completed test.
- Each question includes an `image` field that can be displayed together with the question.
- The `answers` section contains the available answer values together with their corresponding `type` and `icon`.
- Additional fields can be added to the GraphQL Request when they are available in the Documentation Explorer.
- Removing fields reduces the amount of data returned.

---

## Related Examples

---
⬅️ [Invite Study Test](../../Mutations/Invite/Invite_Study_Test.md) |
➡️ [Submit Study Swiper Test Answers](../../Mutations/Submit_Test/Study_Swiper_Test.md)
