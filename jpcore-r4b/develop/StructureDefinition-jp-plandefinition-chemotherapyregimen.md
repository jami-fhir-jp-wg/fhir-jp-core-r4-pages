# JP Core PlanDefinition ChemotherapyRegimen Profile - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core PlanDefinition ChemotherapyRegimen Profile**

## Resource Profile: JP Core PlanDefinition ChemotherapyRegimen Profile 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/StructureDefinition/JP_PlanDefinition_ChemotherapyRegimen
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_PlanDefinition_ChemotherapyRegimen
* **項目**: *Title*
  * **内容**: JP Core PlanDefinition ChemotherapyRegimen Profile
* **項目**: *Status*
  * **内容**: Draft ( 2023-11-30 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
このプロファイルはPlanDefinitionリソースに対して、化学療法レジメンの定義に関する情報を送受信するための共通の制約と拡張を定めたものである。 

本プロファイルは、化学療法レジメンの定義情報を表現するJP_PlanDefinition_ChemotherapyRegimenリソースの記録・更新・検索を行う上で、準拠するべき必須となる要素や、サポートすべき拡張、用語、検索パラメータを定義する。

## スコープ

* JP_PlanDefinition_ChemotherapyRegimenリソースは、化学療法における抗がん剤（注射薬、内服薬）、輸液、支持療法（制吐剤など）の組み合わせと、投与スケジュール、治療期間などを示した計画の情報を表現する。
* 個々の医薬品に関する情報は、JP_ActivityDefinition_ChemotherapyRegimen_Injection および JP_ActivityDefinition_ChemotherapyRegimen_Oralを用いて記述するため、JP_PlanDefinition_ChemotherapyRegimenリソースはcontained要素を用いて、これらのリソースを内包する。
* 化学放射線療法（化学療法と放射線治療の併用）における、放射線治療については、当リソースの対象としない。
* 特定の個人に適用された化学療法レジメンについては、当リソースの対象としない。

## 想定シナリオ

本プロファイルは、以下のようなユースケースを想定する。

* 電子カルテに登録されている化学療法レジメンマスタを他施設に共有する。
* any more

## プロファイル定義

**Usages:**

* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/jpfhir.jp.core|current/StructureDefinition/jp-plandefinition-chemotherapyregimen)

### プロファイル詳細

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-jp-plandefinition-chemotherapyregimen.csv), [Excel](StructureDefinition-jp-plandefinition-chemotherapyregimen.xlsx), [Schematron](StructureDefinition-jp-plandefinition-chemotherapyregimen.sch) 

### 必須要素

本プロファイルに準拠するためには、次の項目の値が存在しなければならない。

*  

| | | | |
| :--- | :--- | :--- | :--- |
| status : 本リソースのステータス (draft | active | retired | unknown) |

 

### Extensions定義

本プロファイルで定義された拡張は次の通りである。

| | | | |
| :--- | :--- | :--- | :--- |
| レジメン種別 | レジメン種別の情報を格納する拡張 | [JP_PlanDefinition_ChemotherapyRegimen_RegimenType](StructureDefinition-jp-plandefinition-chemotherapyregimen-regimentype.md) | CodeableConcept |
| 相対投与日 | 開始日からの相対的な投与日付を表現する拡張《action配下》 | [JP_PlanDefinition_ChemotherapyRegimen_TimingDaysOfCycle](StructureDefinition-jp-plandefinition-chemotherapyregimen-timingdaysofcycle.md) | integer |

### 用語定義

TBD

| | | | |
| :--- | :--- | :--- | :--- |
| レジメン種別 | TBD | TBD | TBD |

### 制約一覧

本プロファイルで追加定義された制約はない。

### 項目の追加

本プロファイルで追加された項目は以下の通りである。

* レジメン種別（拡張「JP_PlanDefinition_ChemotherapyRegimen_RegimenType」を使用）
* 相対投与日（拡張「JP_PlanDefinition_ChemotherapyRegimen_TimingDaysOfCycle」を使用）

## 利用方法

### OperationおよびSearch Parameter 一覧

#### Search Parameter一覧

##### 必須検索パラメータ

本プロファイルに準拠するためには、以下の検索パラメータをサポートしなければならない（SHALL）

1. 検索パラメータidentifierを指定し、レコードIDなどの識別子によりPlanDefinitionを検索

```
GET [base]/PlanDefinition?identifier={system|}[code]

```

例：

```
GET [base]/PlanDefinition?identifier=http://myhospital.com/fhir/PlanDefinition|123

```

指定された識別子に一致するPlanDefinitionリソースを含むBundleを検索する。

##### 推奨検索パラメータ

TBD

##### オプション検索パラメータ

本プロファイルで追加定義されたオプション検索パラメータはない。

#### サンプル

* [**病名（過敏性大腸炎の初期疾患）**](Condition-jp-condition-diagnosis-example-1.md)

## 注意事項

### 薬剤の記述方法

注射薬の場合は JP_ActivityDefinition_ChemotherapyRegimen_Injection を、内服薬の場合は JP_ActivityDefinition_ChemotherapyRegimen_Oral を用いて記述する。 1つの薬剤に対して1つのインスタンスを生成し、当リソースのcontained要素に含め、action#definitionCanonicalとの関連付けを行うこと。

「注射薬Ａ+輸液Ｂ」と「内服薬Ｃ」の組み合わせを表現したインスタンス例を示す。 ＊全体像を掴むためのサンプルであるため、薬剤以外の詳細な記述は省略する。

```
{
  "resourceType" : "PlanDefinition",
  "contained" : [
    {
      "resourceType" : "ActivityDefinition",
      "id" : "1111",
      "contained": [
        {
          "resourceType": "Medication",
          "id": "#1",
          "ingredient": [
            { "itemCodeableConcept": { "text": "注射薬Ａ" } }, 
            { "itemCodeableConcept": { "text": "輸液Ｂ" } }
          ]
        },
      ],
      "productReference": { "reference": "Medication/1" }
    },
    {
      "resourceType" : "ActivityDefinition",
      "id" : "2222",
      "productCodeableConcept" : { "text" : "内服薬Ｃ" }
    }
  ],
  "action" : [
    {
      "action": [
        { "definitionCanonical" : "#1111" },
        { "definitionCanonical" : "#2222" }
      ]
    }
  ]
}

```

### レジメン種別の記述方法

レジメン種別を識別するコードと名称は、PlanDefinitionに対して定義した拡張「JP_PlanDefinition_ChemotherapyRegimen_RegimenType」を使用し、CodeableConcept型を使用して記録する。

TODO: バインドする用語集は検討中

```
"extension": [{
  "url": "http://jpfhir.jp/fhir/core/Extension/StructureDefinition/JP_PlanDefinition_ChemotherapyRegimen_RegimenType",
  "valueCodeableConcept": {
    "coding": [{ 
      "system": "TBD", 
      "code": "TBD", 
      "display": "mFOLFOX6" 
    }],
    "text": "mFOLFOX6"
  }
}]

```

### 適応疾患(がんの種類)の記述方法

TODO: 例えばFOLFOXの場合、「大腸癌」と記述するか、それとも「上行結腸癌」「横行結腸癌」「下行結腸癌」「S状結腸癌」などと細分化して記述するか。また修飾語はJP_Conditionを真似するか。

```
"useContext": [
  {
    "code": {
      "system": "http://terminology.hl7.org/CodeSystem/usage-context-type",
      "code": "focus"
    },
    "valueCodeableConcept": {
      "coding": [
        {
          "system": "TBD",
          "code": "12345"
        }
      ],
      "text": "〇〇癌"
    }
  }
]

```

### 1コースの期間と、サイクル数

投与期間と休薬期間を合わせた1周期(コース)の日数をPlanDefinition.action.timingTiming.repeat.duration要素に記録する。また、コースの繰り返し回数(サイクル数)をPlanDefinition.action.timingTiming.repeat.count要素に記録する。 人間が解釈可能な1コースの期間と、サイクル数のテキスト表現をPlanDefinition.action.textEquivalentに記録する。

「1コース14日を6サイクル繰り返す」のインスタンス例を示す。

```
"action": [
  {
    "textEquivalent": "1コース14日を6サイクル繰り返す",
    "timingTiming": {
      "repeat": {
        "count": 6,
        "duration": 14,
        "durationUnit": "d"
      }
    }
  }
]

```

「1コース14日を4〜6サイクル繰り返す」のように、サイクル数に幅がある場合、PlanDefinition.action.timingTiming.repeat.countに繰り返し回数の下限を記録し、PlanDefinition.action.timingTiming.repeat.countMaxに上限を記録する。

TODO: 繰り返し数未定（できる限り継続する、PDまでなど）の場合はどうするか。

```
"action": [
  {
    "textEquivalent": "1コース14日を4〜6サイクル繰り返す",
    "timingTiming": {
      "repeat": {
        "count": 4,
        "countMax": 6,
        "duration": 14,
        "durationUnit": "d"
      }
    }
  }
]

```

### 相対投与日の記述方法

投与開始日からの相対的な投与日を、PlanDefinition.actionに定義した拡張「JP_PlanDefinition_ChemotherapyRegimen_TimingDaysOfCycle」を使用し、integer型を使用して記録する。

「day1 と day8」に投与する場合のインスタンス例を示す。

```
"action": [{
  "extension": [
    {
      "url": "http://hl7.org/fhir/StructureDefinition/timing-daysOfCycle",
      "valueInteger": 1
    },
    {
      "url": "http://hl7.org/fhir/StructureDefinition/timing-daysOfCycle",
      "valueInteger": 8
    }
  ]
}]

```

### 投与順序の記述方法

TBD

### 発行元

TODO</br> 外部公開することを考えると、発行元(医療機関名等)を記載しておくことが望ましいと思われる。</br> jurisdictionだと少し範囲が大きすぎる気がするし、publisherはstring型なのでテキストでしか記載できない。
## その他、参考文献・リンク等

TBD

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "jp-plandefinition-chemotherapyregimen",
  "url" : "http://jpfhir.jp/fhir/core/StructureDefinition/JP_PlanDefinition_ChemotherapyRegimen",
  "version" : "2.0.0-dev",
  "name" : "JP_PlanDefinition_ChemotherapyRegimen",
  "title" : "JP Core PlanDefinition ChemotherapyRegimen Profile",
  "status" : "draft",
  "date" : "2023-11-30",
  "publisher" : "FHIR Japanese implementation research working group in Japan Association of Medical Informatics (JAMI)",
  "contact" : [
    {
      "name" : "FHIR Japanese implementation research working group in Japan Association of Medical Informatics (JAMI)",
      "telecom" : [
        {
          "system" : "url",
          "value" : "http://jpfhir.jp"
        },
        {
          "system" : "email",
          "value" : "office@hlfhir.jp"
        }
      ]
    }
  ],
  "description" : "このプロファイルはPlanDefinitionリソースに対して、化学療法レジメンの定義に関する情報を送受信するための共通の制約と拡張を定めたものである。",
  "jurisdiction" : [
    {
      "coding" : [
        {
          "system" : "urn:iso:std:iso:3166",
          "code" : "JP",
          "display" : "Japan"
        }
      ]
    }
  ],
  "copyright" : "Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会",
  "fhirVersion" : "4.3.0",
  "mapping" : [
    {
      "identity" : "workflow",
      "uri" : "http://hl7.org/fhir/workflow",
      "name" : "Workflow Pattern"
    },
    {
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
    },
    {
      "identity" : "w5",
      "uri" : "http://hl7.org/fhir/fivews",
      "name" : "FiveWs Pattern Mapping"
    },
    {
      "identity" : "objimpl",
      "uri" : "http://hl7.org/fhir/object-implementation",
      "name" : "Object Implementation Information"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "PlanDefinition",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/PlanDefinition",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "PlanDefinition",
        "path" : "PlanDefinition",
        "short" : "TBD",
        "definition" : "TBD"
      },
      {
        "id" : "PlanDefinition.extension",
        "path" : "PlanDefinition.extension",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "url"
            }
          ],
          "ordered" : false,
          "rules" : "open"
        }
      },
      {
        "id" : "PlanDefinition.extension:regimenType",
        "path" : "PlanDefinition.extension",
        "sliceName" : "regimenType",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://jpfhir.jp/fhir/core/Extension/StructureDefinition/JP_PlanDefinition_ChemotherapyRegimen_RegimenType"
            ]
          }
        ]
      },
      {
        "id" : "PlanDefinition.useContext",
        "path" : "PlanDefinition.useContext",
        "short" : "【仮】対象疾患"
      },
      {
        "id" : "PlanDefinition.action.extension",
        "path" : "PlanDefinition.action.extension",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "url"
            }
          ],
          "ordered" : false,
          "rules" : "open"
        }
      },
      {
        "id" : "PlanDefinition.action.extension:timingDaysOfCycle",
        "path" : "PlanDefinition.action.extension",
        "sliceName" : "timingDaysOfCycle",
        "min" : 0,
        "max" : "*",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/StructureDefinition/timing-daysOfCycle|5.2.0"
            ]
          }
        ]
      },
      {
        "id" : "PlanDefinition.action.timing[x]",
        "path" : "PlanDefinition.action.timing[x]",
        "short" : "【仮】総サイクル（n日サイクルを n回繰り返す等）",
        "comment" : "\n例: 14日サイクルを12回繰り返す\ntimingTiming : {\n  repeat : {\n    count : 12,\n    duration : 14,\n    durationUnit : d\n  }\n}\n",
        "type" : [
          {
            "code" : "Timing"
          }
        ]
      },
      {
        "id" : "PlanDefinition.action.definition[x]",
        "path" : "PlanDefinition.action.definition[x]",
        "short" : "【仮】医薬品情報のActivityDefinitionを参照する",
        "type" : [
          {
            "code" : "canonical",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_ActivityDefinition_ChemotherapyRegimen_Injection",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_ActivityDefinition_ChemotherapyRegimen_Oral"
            ]
          }
        ]
      }
    ]
  }
}

```
