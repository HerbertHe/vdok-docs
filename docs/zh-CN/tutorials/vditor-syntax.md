---
title: Vditor 拓展语法
---

## Vditor 拓展语法

此章节为 Vditor 基于通用 Markdown 语法的拓展实现, 并非通用语法, 因此极多的渲染器和编辑器仅实现了其中的**一部分**语法特性, Vditor 同样不支持部分特性。

Vdok 基于 Vditor **深度定制**开发, **渲染结果与 Vditor 并不完全一致**, 仅为兼容 Vditor 的实现 (后期可能会有并不兼容之处。如果您发现了冲突之处或者希望支持的部分, 请通过 [GitHub Issues](https://github.com/HerbertHe/vdok/issues) 进行反馈)。

## 标题自定义锚点

> Vditor 的 `v3.8.5` 并没有暴露设置自定义锚点给自定义渲染器实现, 因此下面的实现为 hack 的自定义实现, 请使用下面的标准语法, 否则可能会导致某些错误产生。

```markdown
# 标题 {\#自定义锚点}

# 标题 {\#heading}

\ 为转义符号, 写文档时请忽略。
```

## 公式

公式渲染通过 [$\KaTeX$](https://katex.org/) 实现。

### 行内公式

```markdown
质能方程: $E = mc^2$, 薛定谔方程: $\hat H \Psi=i \hbar \frac{\partial}{\partial t}\Psi$
```

输出:

质能方程: $E = mc^2$, 薛定谔方程: $\hat H \Psi=i \hbar \frac{\partial}{\partial t}\Psi$

### 公式块

```markdown
$$
\nabla \times H = J + \frac{\partial D}{\partial t} \newline
\nabla \times E = - \frac{\partial B}{\partial t} \newline
\nabla \cdot B = 0 \newline
\nabla \cdot D = \rho
$$
```

输出:

$$
\nabla \times H = J + \frac{\partial D}{\partial t} \newline
\nabla \times E = - \frac{\partial B}{\partial t} \newline
\nabla \cdot B = 0 \newline
\nabla \cdot D = \rho
$$

## 脑图 Mindmap

````markdown
```mindmap
- Vdok
  - Author
    - Herbert He
  - Technology stack
    - Vditor
    - Vite
    - React
    - Windi CSS
```
````

输出:

```mindmap
- Vdok
  - Author
    - Herbert He
  - Technology stack
    - Vditor
    - Vite
    - React
    - Windi CSS
```

## Echarts

## Mermaid

下面的图形通过 [Mermaid](https://mermaid-js.github.io/mermaid/#/) 实现, 所有的示例均来自于 Mermaid 示例。

> 更多 Mermaid 语法, 请参考 [Mermaid](https://mermaid-js.github.io/mermaid/#/) 文档。

### 流程图

````markdown
```mermaid
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```
````

```mermaid
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```

### 时序图

````markdown
```mermaid
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```
````

```mermaid
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

### 类图

````markdown
```mermaid
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```
````

```mermaid
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```

### 状态图

````markdown
```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
````

```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

### ER 模型

````markdown
```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```
````

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

### 用户旅途

````markdown
```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```
````

```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

### 甘特图

````markdown
```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```
````

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

### 饼图

````markdown
```mermaid
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```
````

```mermaid
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```

### 需求图

> 测试中！

````markdown
```mermaid
requirementDiagram
    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    element test_entity {
    type: simulation
    }

    test_entity - satisfies -> test_req
```
````

## Graphviz

## Plantuml UML图

## 五线谱
