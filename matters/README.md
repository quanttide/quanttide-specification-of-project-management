# 事项

事项子领域的核心模型是事项领域模型`Matter`。

REST API如下：

- list: `/matters`
- detail: `/matters/<number>`

包括字段如下，未说明字段为标准字段：

- `id`
- `number`
- `type`: 类型。选项见[事项类型](./type.md)
