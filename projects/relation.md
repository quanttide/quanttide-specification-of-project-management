# 项目关联关系

## 项目关系模型`ProjectRelation`

项目关系遵循有向无环图(DAG)建模。
从DAG的视角，`Project`和`ProjectRelation`分别为它的节点(Node)和边(Edge)，以此理解`ProjectRelation`模型的作用。

### 子模型字段`child`

`Project`模型的`id`字段。

### 父模型字段`parent`

`Project`模型的`id`字段。

## REST API

- list: `/project-relations`
- detail: `/project-relations/<id>`
