# JP Core ActivityDefinition ChemotherapyRegimen Oral Profile - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev-temp

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core ActivityDefinition ChemotherapyRegimen Oral Profile**

## Resource Profile: JP Core ActivityDefinition ChemotherapyRegimen Oral Profile 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/StructureDefinition/JP_ActivityDefinition_ChemotherapyRegimen_Oral
* **項目**: *Version*
  * **内容**: 2.0.0-dev-temp
* **項目**: *Name*
  * **内容**: JP_ActivityDefinition_ChemotherapyRegimen_Oral
* **項目**: *Title*
  * **内容**: JP Core ActivityDefinition ChemotherapyRegimen Oral Profile
* **項目**: *Status*
  * **内容**: Draft ( 2023-11-30 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
このプロファイルはActivityDefinitionリソースに対して、化学療法レジメンの定義に関する情報を送受信するための共通の制約と拡張を定めたものである。 

**Usages:**

* Refer to this Profile: [JP Core PlanDefinition ChemotherapyRegimen Profile](StructureDefinition-jp-plandefinition-chemotherapyregimen.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/jpfhir.jp.core|current/StructureDefinition/jp-activitydefinition-chemotherapyregimen-oral)

### プロファイル詳細

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-jp-activitydefinition-chemotherapyregimen-oral.csv), [Excel](StructureDefinition-jp-activitydefinition-chemotherapyregimen-oral.xlsx), [Schematron](StructureDefinition-jp-activitydefinition-chemotherapyregimen-oral.sch) 

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "jp-activitydefinition-chemotherapyregimen-oral",
  "url" : "http://jpfhir.jp/fhir/core/StructureDefinition/JP_ActivityDefinition_ChemotherapyRegimen_Oral",
  "version" : "2.0.0-dev-temp",
  "name" : "JP_ActivityDefinition_ChemotherapyRegimen_Oral",
  "title" : "JP Core ActivityDefinition ChemotherapyRegimen Oral Profile",
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
  "description" : "このプロファイルはActivityDefinitionリソースに対して、化学療法レジメンの定義に関する情報を送受信するための共通の制約と拡張を定めたものである。",
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
  "type" : "ActivityDefinition",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/ActivityDefinition",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "ActivityDefinition",
        "path" : "ActivityDefinition",
        "short" : "TBD",
        "definition" : "TBD"
      },
      {
        "id" : "ActivityDefinition.product[x]",
        "path" : "ActivityDefinition.product[x]",
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "binding" : {
          "strength" : "preferred",
          "description" : "医薬品コード",
          "valueSet" : "http://jpfhir.jp/fhir/core/ValueSet/JP_MedicationCode_VS"
        }
      },
      {
        "id" : "ActivityDefinition.dosage",
        "path" : "ActivityDefinition.dosage",
        "type" : [
          {
            "code" : "Dosage",
            "profile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_MedicationDosage"
            ]
          }
        ]
      }
    ]
  }
}

```
