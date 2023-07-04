# 项目类型和关联关系

## 项目类型

定义“项目集`Program`”和“项目组合`ProjecPortfolio`”为“项目`Project`”的子类。
在项目管理理论中，“项目”有狭义和广义两种表述方式，狭义的项目可以是项目集和项目组合的组成部分，广义的项目是他们的总称。
我们这里采纳了广义的表述，并且让项目集和项目组合拥有项目的绝大多数特性，以支持更复杂的项目边界划分策略。

使用`type`字段标记具体子类，选项包括：

- `default`: 默认
- `program`: 项目集
- `project_portfolio`: 项目组合

代码示例：

`````{tab-set}
````{tab-item} Django
```{code-block} python
from django.db import models

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

## 项目关系模型`ProjectRelation`

项目关系遵循有向无环图(DAG)建模。
从DAG的视角，`Project`和`ProjectRelation`分别为它的节点(Node)和边(Edge)，以此理解`ProjectRelation`模型的作用。

### 子模型字段`child`

`Project`模型的`id`字段。

### 父模型字段`parent`

`Project`模型的`id`字段。

### REST API

- list: `/project-relations`
- detail: `/project-relations/<id>`
