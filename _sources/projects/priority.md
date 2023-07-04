# 项目优先级

## 选项

- `low`: 低
- `middle`: 中
- `high`: 高
- `urgent`: 紧急

`````{tab-set}
````{tab-item} Django
```{code-block} python
from django.db import models

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