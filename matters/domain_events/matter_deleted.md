# 事项已删除`MatterDeleted`

该领域事件表示事项被删除的事件。

## 属性

- `matter_id`（唯一标识符）：被删除的事项的唯一标识符。
- `deleted_by`（字符串）：执行删除操作的用户或系统标识符。
- `deleted_at`（日期时间）：删除操作发生的日期和时间。

## 示例

```json
{
  "event_type": "MatterDeleted",
  "matter_id": 12345,
  "deleted_by": "user123",
  "deleted_at": "2023-09-13 11:00:00"
}
```
