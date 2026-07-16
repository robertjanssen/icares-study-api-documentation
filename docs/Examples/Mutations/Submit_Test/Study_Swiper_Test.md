[Documentation](../../../README.md) > [Examples](../../README.md) > [Mutations](../README.md) > **Submit Tests**
# Study Swiper Test

## Purpose

Submits the completed answers for a **Study Swiper Test**.

Each submitted answer consists of a question identifier (`id`) and the selected answer (`value`).

---

## GraphQL Request

```graphql
mutation submitStudySwiperTestAnswer
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

Replace `<< test id >>` with the identifier returned by the **Invite Study Test** mutation for a `study_swiper_test`.

```json
{
  "id": << test id >>,
  "answers": [
    { "id": 1201, "value": "0" },
    { "id": 1202, "value": "1" },
    { "id": 1203, "value": "2" },
    { "id": 1204, "value": "0" },
    { "id": 1205, "value": "1" },
    { "id": 1206, "value": "2" },
    { "id": 1207, "value": "0" },
    { "id": 1208, "value": "1" },
    { "id": 1209, "value": "2" },
    { "id": 1210, "value": "0" },
    { "id": 1211, "value": "1" },
    { "id": 1212, "value": "2" },
    { "id": 1213, "value": "0" },
    { "id": 1214, "value": "1" },
    { "id": 1215, "value": "2" },
    { "id": 1216, "value": "0" },
    { "id": 1217, "value": "1" },
    { "id": 1218, "value": "2" },
    { "id": 1219, "value": "0" },
    { "id": 1220, "value": "1" },
    { "id": 1221, "value": "2" },
    { "id": 1222, "value": "0" },
    { "id": 1223, "value": "1" },
    { "id": 1224, "value": "2" },
    { "id": 1225, "value": "0" },
    { "id": 1226, "value": "1" },
    { "id": 1227, "value": "2" },
    { "id": 1228, "value": "0" },
    { "id": 1229, "value": "1" },
    { "id": 1230, "value": "2" },
    { "id": 1231, "value": "0" },
    { "id": 1232, "value": "1" },
    { "id": 1233, "value": "2" },
    { "id": 1234, "value": "0" },
    { "id": 1235, "value": "1" },
    { "id": 1236, "value": "2" },
    { "id": 1237, "value": "0" },
    { "id": 1238, "value": "1" },
    { "id": 1239, "value": "2" },
    { "id": 1240, "value": "0" },
    { "id": 1241, "value": "1" },
    { "id": 1242, "value": "2" },
    { "id": 1243, "value": "0" },
    { "id": 1244, "value": "1" },
    { "id": 1245, "value": "2" },
    { "id": 1246, "value": "0" },
    { "id": 1247, "value": "1" },
    { "id": 1248, "value": "2" },
    { "id": 1249, "value": "0" },
    { "id": 1250, "value": "1" },
    { "id": 1251, "value": "2" },
    { "id": 1252, "value": "0" },
    { "id": 1253, "value": "1" },
    { "id": 1254, "value": "2" },
    { "id": 1255, "value": "0" },
    { "id": 1256, "value": "1" },
    { "id": 1257, "value": "2" },
    { "id": 1258, "value": "0" },
    { "id": 1259, "value": "1" },
    { "id": 1260, "value": "2" },
    { "id": 1261, "value": "0" },
    { "id": 1262, "value": "1" },
    { "id": 1263, "value": "2" },
    { "id": 1264, "value": "0" },
    { "id": 1265, "value": "1" },
    { "id": 1266, "value": "2" },
    { "id": 1267, "value": "0" },
    { "id": 1268, "value": "1" },
    { "id": 1269, "value": "2" },
    { "id": 1270, "value": "0" },
    { "id": 1271, "value": "1" },
    { "id": 1272, "value": "2" },
    { "id": 1273, "value": "0" },
    { "id": 1274, "value": "1" },
    { "id": 1275, "value": "2" },
    { "id": 1276, "value": "0" },
    { "id": 1277, "value": "1" },
    { "id": 1278, "value": "2" },
    { "id": 1279, "value": "0" },
    { "id": 1280, "value": "1" },
    { "id": 1281, "value": "2" }
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
- The question identifiers shown in this example are specific to the **Study Swiper Test**.
- The answer values used in this test are `0`, `1` and `2`.
- Use the question identifiers and answer values from the corresponding test form when constructing the request.
- Other study tests use different question identifiers and answer structures.

---

## Related Examples

Previous steps:

- **Mutations → Invite → Invite Study Test**
- **Queries → Forms → Study Swiper Test**

Next step:

- **Queries → Results**
