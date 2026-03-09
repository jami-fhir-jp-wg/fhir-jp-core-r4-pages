# JP Core Condition Disease Code MEDIS Exchange CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Code MEDIS Exchange CodeSystem**

## CodeSystem: JP Core Condition Disease Code MEDIS Exchange CodeSystem 

* **項目**: *定義URL*
  * **内容**: urn:oid:1.2.392.200119.4.101.6
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ConditionDiseaseCodeMEDISExchange_CS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Code MEDIS Exchange CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: Copyright MEDIS-DC 医療情報システム開発センター

 
MEDIS ICD10対応標準病名マスター(交換用コード) コードシステム 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ConditionDiseaseCodeMEDISExchange_VS](ValueSet-jp-condition-disease-code-medis-exchange-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-condition-disease-code-medis-exchange-cs",
  "url" : "urn:oid:1.2.392.200119.4.101.6",
  "version" : "2.0.0-dev",
  "name" : "JP_ConditionDiseaseCodeMEDISExchange_CS",
  "title" : "JP Core Condition Disease Code MEDIS Exchange CodeSystem",
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
  "description" : "MEDIS ICD10対応標準病名マスター(交換用コード) コードシステム",
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
      "code" : "HR19",
      "display" : "急性化膿性虫垂炎"
    },
    {
      "code" : "VSES",
      "display" : "大腸炎"
    }
  ]
}

```
