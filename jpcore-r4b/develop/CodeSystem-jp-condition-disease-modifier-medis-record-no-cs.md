# JP Core Condition Disease Modifier MEDIS Record CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Modifier MEDIS Record CodeSystem**

## CodeSystem: JP Core Condition Disease Modifier MEDIS Record CodeSystem 

* **項目**: *定義URL*
  * **内容**: urn:oid:1.2.392.200119.4.201.2
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ConditionDiseaseModifierMEDISRecordNo_CS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Modifier MEDIS Record CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: Copyright MEDIS-DC 医療情報システム開発センター

 
MEDIS ICD10対応標準病名マスター(修飾語管理番号) コードシステム 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ConditionDiseaseModifierMEDISRecordNo_VS](ValueSet-jp-condition-disease-modifier-medis-record-no-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-condition-disease-modifier-medis-record-no-cs",
  "url" : "urn:oid:1.2.392.200119.4.201.2",
  "version" : "2.0.0-dev",
  "name" : "JP_ConditionDiseaseModifierMEDISRecordNo_CS",
  "title" : "JP Core Condition Disease Modifier MEDIS Record CodeSystem",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-08-05",
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
  "description" : "MEDIS ICD10対応標準病名マスター(修飾語管理番号) コードシステム",
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
  "copyright" : "Copyright MEDIS-DC 医療情報システム開発センター",
  "caseSensitive" : true,
  "content" : "fragment",
  "concept" : [
    {
      "code" : "27000267",
      "display" : "過敏性"
    },
    {
      "code" : "27000027",
      "display" : "の初期"
    },
    {
      "code" : "27001344",
      "display" : "疾患"
    }
  ]
}

```
