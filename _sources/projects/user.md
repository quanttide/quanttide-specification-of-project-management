# 项目成员

## 背景

描述项目的负责人及其所属的负责组。

- 负责人 Owner 代表 负责部委。通常是项目管理权限。
- 复核人 Reviewer 代表 复核部委。通常是汇报链条的上级，或者同级的副手，少部分情况可能是辅助的下级。通常是项目管理权限。
- 参与者 Member 来自 参与部委。通常是内部维护者。通常拥有读写权限。
- 关注者 Observer 来自 关注部委。通常是内部用户，比如文档的读者。通常只有读权限。


## 项目成员关联模型`ProjectUserRelation`

项目成员关联模型 ProjectUserRelation 用于描述项目参与者之间的关系。该模型定义了项目成员及其在项目中的角色和权限。

### 属性

- `id`: 关联模型的唯一标识符。
- `created_at`
- `updated_at`
- `project_id`: 项目的唯一标识符，用于指示该关联属于哪个项目。
- `user_id`: 用户的唯一标识符，用于指示该关联属于哪个用户。
- `group_id`: 组织用户组的唯一标识符，用来指示该关联用户代表哪个组织用户组。
- `role`: 项目成员的角色。可以是固定预定义的角色，也可以根据具体项目的需要进行自定义。

### 关联关系

- `project`: 外键关联。该关联所属的项目。
- `user`: 外键关联。该关联所属的用户。
- `group`: 外键关联。该关联所属的组织用户组。

### 示例代码

`````{tab-set}
````{tab-item} Django
```{code-block} python
from django.db import models as models
from django_quanttide import models as quanttide_models
# 补充数据模型导入。i.e.
# from <> import Project, User, ProjectUserRole

class ProjectUserRelation(models.Model):
    created_at = quanttide_models.CreatedAt()
    updated_at = quanttide_models.UpdatedAt()
    project = models.ForeignKey(Project, on_delete=models.CASCADE, verbose_name='关联项目')
    user = models.ForeignKey(User, on_delete=models.CASCADE, verbose_name='关联用户')
    group = models.ForeignKey(OrganizationUserGroup, null=True, on_delete=models.SET_NULL, verbose_name='关联组织用户组')
    role = models.ForeignKey(ProjectUserRole, on_delete=models.SET_NULL, verbose_name='关联角色')
```
````
`````

## 项目成员角色模型`ProjectUserRole`

定义项目中可供选择的角色选项。该模型包含了项目成员在项目中可能担任的各种角色，以及每个角色可能具备的权限和责任。

### 属性

- `id`: 角色模型的唯一标识符。
- `created_at`
- `updated_at`
- `name`: 角色的标识。例如`owner`、`reviewer`、`member`、`observer`等。
- `verbose_name`: 角色的名称。例如"负责人"、"复核人"、"参与者"、"关注者"等。
- `description`: 角色的描述，提供关于该角色职责和权限的详细信息。

### 示例代码

`````{tab-set}
````{tab-item} Django
```{code-block} python
from django_quanttide import models

class ProjectUserRole(models.Model):
    name = models.NameField()
    created_at = models.CreatedAt()
    updated_at = models.UpdatedAt()
    verbose_name = models.VerboseNameField()
    description = models.DescriptionField()
```
````
`````
