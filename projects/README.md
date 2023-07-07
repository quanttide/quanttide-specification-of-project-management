# 项目

本章定义项目子领域。

## 项目模型`Project`

项目子领域的基本模型为项目模型`Project`。

包括如下字段，其中未说明为标准字段：

- `id`
- `name`
- `title`
- `description`
- `created_at`
- `updated_at`
- `type`: 类型。定义见[项目类型](./type.md)
- `hierarchy`: 层级。定义见[项目层级](./hierarchy.md)
- `status`: 状态。定义见[项目生命周期](./lifecycle.md)
- `priority`: 优先级。定义见[项目优先级](./priority.md)

REST API为：

- list: `/projects`
- detail: `/projects/<name>`
