# 事项更新`MatterUpdated`

事项被更新。

### 属性

- `matter_id`（唯一标识符）：被更新的事项的唯一标识符。
- `updated_fields`（列表）：包含被更新的字段名称的列表。
- `updated_values`（列表）：包含被更新的字段对应的新值的列表。
- `updated_by`（字符串）：执行更新操作的用户或系统标识符。
- `updated_at`（日期时间）：更新操作发生的日期和时间。

### 示例

```json
{
    "event_type": "MatterUpdated",
    "matter_id"："12345"
    "updated_fields"：["title", "description"]
    "updated_values"：["New Title", "New Description"]
    "updated_by"："user123"
    "updated_at"："2023-09-13 15:30:00"
}
```
