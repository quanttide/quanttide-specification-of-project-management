# 项目模型`Project`

定义“项目集”和“项目组合”为“项目”的子类。
在项目管理理论中，“项目”有狭义和广义两种表述方式，狭义的项目可以是项目集和项目组合的组成部分，广义的项目是他们的总称。
我们这里采纳了广义的表述，并且让项目集和项目组合拥有项目的绝大多数特性，以支持更复杂的项目边界划分策略。

## 字段

- `id`
- `name`
- `title`
- `description`
- `type`
- `created_at`
- `updated_at`
- `status`: 状态
- `priority`: 优先级

### 类型选项

- `default`: 默认
- `program`: 项目集
- `project_portfolio`: 项目组合

`````{tab-set}
````{tab-item}
```{code-block} python
class ProjectTypeChoices(models.TextChoices):
    """
    项目类型选项
    """
    default = 'default', '项目'
    program = 'program', '项目集'
    project_portfolio = 'project_portfolio', '项目组合'
```
````
`````

### 优先级选项

- `low`: 低
- `middle`: 中
- `high`: 高
- `urgent`: 紧急

`````{tab-set}
````{tab-item}
```{code-block} python
class PriorityChoices(models.IntegerChoices):
    """
    优先级选项

    类似于logging模块的level选项的设计风格。使用形容词描述。
    """
    LOW = 10, '低'
    MIDDLE = 20, '中'
    HIGH = 30, '高'
    URGENT = 40, '紧急'
```
````
`````

### 状态选项

- `drafting`: 起草中。该状态表示项目或事项处于起草阶段，即正在制定计划和准备工作。
- `evaluating`: 评估中。该状态表示项目或事项正在进行评估，以确定其可行性和实施方案。
- `awaiting`: 等待开始。该状态表示项目或事项已经准备就绪，但尚未开始实施，可能是因为需要等待某些资源或条件。
- `in_progress`: 进行中。该状态表示项目或事项正在进行中，即正在实施并按计划推进。
- `delayed`: 已延迟。该状态表示项目或事项因某种原因而延迟，可能需要重新制定计划或采取其他措施来弥补延迟。
- `paused`: 已暂停。该状态表示项目或事项已经暂停，可能是因为需要等待某些资源或条件，或者因为需要重新评估实施方案。
- `reviewing`: 评审中。该状态表示项目或事项正在接受评审，以检查其进展和结果，可能需要做出一些调整或修正。
- `completed`: 已完成。该状态表示项目或事项已经完成，达到预期的目标和成果。
- `cancelled`: 已取消。该状态表示项目或事项已经取消，可能是因为它不再需要实施，或者因为有更好的替代方案。

`````{tab-set}
````{tab-item}
```{code-block} python
class StatusChoices(models.TextChoices):
    """
    状态选项

    遵循项目和事项的生命周期的定义，使用形容词或动名词描述。
    """
    DRAFT = 'drafting', '起草中'
    EVALUATION = 'evaluating', '评估中'
    AWAITING = 'awaiting', '等待开始'
    IN_PROGRESS = 'in_progress', '进行中'
    DELAYED = 'delayed', '已延迟'
    PAUSED = 'paused', '已暂停'
    REVIEWING = 'reviewing', '评审中'
    DELIVERING = 'delivering', '交付中'
    SUMMARIZING = 'summarizing', '复盘中'
    COMPLETED = 'completed', '已完成'
    CANCELLED = 'cancelled', '已取消'
```
````
`````


## REST API

- list: `/projects`
- detail: `/projects/<name>`
