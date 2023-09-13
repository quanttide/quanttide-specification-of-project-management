# 事项已创建`MatterCreated`

该领域事件表示事项被创建的事件。

## 属性

- `matter_id`（唯一标识符）：新创建的事项的唯一标识符。
- `title`（字符串）：新创建的事项的标题。
- `description`（字符串）：新创建的事项的描述。
- `created_by`（字符串）：执行创建操作的用户或系统标识符。
- `created_at`（日期时间）：创建操作发生的日期和时间。

## 示例

{
  "event_type": "MatterCreated",
  "matter_id": 12345,
  "title": "New Matter",
  "description": "This is a new matter.",
  "created_by": "user123",
  "created_at": "2023-09-13 10:00:00"
}
