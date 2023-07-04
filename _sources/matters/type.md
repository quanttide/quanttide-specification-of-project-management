# 事项类型

## 类型选项

- `default`: 事项。该类型表示一般的事项或任务，通常是项目中最基本的单位，可以是某项工作、某个功能点或某个问题等。
- `millstone`: 里程碑。该类型表示项目中的重要节点或阶段，通常与项目计划和时间表密切相关，用于标识项目的进展和里程碑。
- `epic`: 史诗。该类型通常用于敏捷开发中，表示一个大型的、跨部门或跨团队的用户需求，可以包含多个用户故事。
- `story`: 用户故事。该类型通常用于敏捷开发中，表示一个用户的需求或期望，通常以用户的角度来描述，用于指导开发人员的工作。
- `task`: 任务。该类型表示具体的工作项或任务，通常是项目中最基本的单位，可以是某项工作、某个功能点或某个问题等。
- `defect`: 缺陷。该类型表示产品或系统中的问题或缺陷，通常需要进行修复或调整，以提高产品或系统的质量和性能。

`````{tab-set}
````{tab-item} Django
```{code-block} python
from django.db import models

class MatterTypeChoices(models.TextChoices):
    """
    事项类型选项
    """
    default = 'default', '事项'
    millstone = 'millstone', '里程碑'
    epic = 'epic', '史诗'
    story = 'story', '用户故事'
    task = 'task', '任务'
    defect = 'defect', '缺陷'
```
````
`````
