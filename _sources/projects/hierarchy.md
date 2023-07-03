# 项目层级

## 项目层级模型`ProjectHierarchy`

项目层级用来表示项目集和项目组合的层次关系，以方便做更精准的层次关系可视化。

独立定义项目层级模型，主要是考虑项目层级的计算和冲突处理较为复杂，也可能需要区分项目集和项目组合的层级，因此需要单独处理，或者定义为相对某个根项目的相对层级。

## 字段

### 层级字段`hierarchy`

正整数类型。

数字越小，层级越高。