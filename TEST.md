# TEST IT

<!-- @import "[TOC]" {cmd="toc" depthFrom=2 depthTo=3 orderedList=false} -->
<!-- code_chunk_output -->

* [Test Svg](#test-svg)
* [Test Markdown All-in-one plugin](#test-markdown-all-in-one-plugin)
* [Test gravizo](#test-gravizo)
* [Test Sequence Diagrams](#test-sequence-diagrams)
* [test mermaid](#test-mermaid)
* [test plantuml](#test-plantuml)

<!-- /code_chunk_output -->

## Test Svg

<svg>
    <a xlink:href="http://www.w3.org//Graphics//SVG//Overview.htm8">
        <rect x="10" y="10" width="100" height="30" rx="10" ry="10"
              style="fill:lightgrey"/>
        <text x="30" y="30" font-size="12">Click here</text>
    </a>
    <a xlink:href="http://www.ibm.com//developerworks/">
        <circle cx="100" cy="100" r="50" style="fill:grey"/>
        <text x="80" y="100" font-size="12">Or here</text>
    </a>
    <a xlink:href="http://www.ibm.com/" target="new">
        <polygon
              points="60 160,165 172,180 60,290 290,272 280,172 285,250 255"
              style="fill:dimgrey"/>
        <text x="160" y="200" font-size="12">Or even here</text>
    </a>
</svg>


## Test Markdown All-in-one plugin

{汉|han}

## Test gravizo

test **<https://g.gravizo.com/svg?>...**，在线生成各种图：

![Alt text](https://g.gravizo.com/svg?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> {parse [weight=8]; d; cleanup, init [style=dotted]; printf [style=bold,label="100 times"]};
    parse -> execute;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)

## Test Sequence Diagrams

```sequence
cc-->bb: Hello
note right of bb: This is a question
```

## test mermaid

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## test plantuml

```plantuml
@startuml test01
  a-->b: hello
  b-->c: how are you
  c-->d: end
@enduml
```

```plantuml
@startuml test02

package "组件1" {
    ["组件1.1"] - ["组件1.2"]
    ["组件1.2"] -> ["组件2.1"]
}

node "组件2" {
    ["组件2.1"] - ["组件2.2"]
    ["组件2.2"] --> [负载均衡服务器]
}

cloud {
    [负载均衡服务器] -> [逻辑服务器1]
    [负载均衡服务器] -> [逻辑服务器2]
    [负载均衡服务器] -> [逻辑服务器3]
}

database "MySql" {
    folder "This is my folder" {
        [Folder 3]
    }

    frame "Foo" {
        [Frame 4]
    }
}

[逻辑服务器1] --> [Folder 3]
[逻辑服务器2] --> [Frame 4]
[逻辑服务器3] --> [Frame 4]

@enduml
```

```plantuml
@startuml test03
archimate #Technology "VPN Server" as vpnServerA <<technology-device>>

rectangle GO #lightgreen
rectangle STOP #red
rectangle WAIT #orange

GO->STOP
@enduml
```

```plantuml
@startuml
!includeurl https://raw.githubusercontent.com/ebbypeter/Archimate-PlantUML/master/Archimate.puml

title Archimate Sample - Requirement & Application Services

'Elements'
Motivation_Requirement(ReqPayrollStandard, "Do Payroll with a standard system")
Motivation_Requirement(ReqBudgetPlanning, "Do budget planning within the ERP system")

Application_Service(ASPayroll,"Payroll Service")
Application_Service(ASBudgetPlanning,"Budget Planning Service")
Application_Component(ACSAPFinanceAccRec, "SAP Finance - Accounts Recievables")
Application_Component(ACSAPHR, "SAP Human Resources")
Application_Component(ACSAPFin, "SAP Finance")
Application_Component(ACSAP,"SAP")

'Relationships'
Rel_Realization_Up(ASPayroll, ReqPayrollStandard)
Rel_Realization_Up(ASBudgetPlanning, ReqBudgetPlanning)
Rel_Realization_Up(ACSAPFinanceAccRec, ASBudgetPlanning)
Rel_Realization_Up(ACSAPHR, ASPayroll)

Rel_Composition_Up(ACSAPFin, ACSAPFinanceAccRec)
Rel_Composition_Up(ACSAP, ACSAPHR)
Rel_Composition_Up(ACSAP, ACSAPFin)
@enduml
```
