# JP Core Condition Disease Modifier Receipt System CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Modifier Receipt System CodeSystem**

## CodeSystem: JP Core Condition Disease Modifier Receipt System CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_ConditionDiseaseModifierReceipt_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ConditionDieaseModifierReceipt_CS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Modifier Receipt System CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: Copyright 社会保険診療報酬支払基金

 
レセプト電算用修飾語マスター コードシステム 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ConditionDiseaseModifierMEDISExchange_VS](ValueSet-jp-condition-disease-modifier-medis-exchange-vs.md)
* [JP_ConditionDiseaseModifierReceipt_VS](ValueSet-jp-condition-disease-modifier-receipt-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-condition-disease-modifier-receipt-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_ConditionDiseaseModifierReceipt_CS",
  "version" : "2.0.0-dev",
  "name" : "JP_ConditionDieaseModifierReceipt_CS",
  "title" : "JP Core Condition Disease Modifier Receipt System CodeSystem",
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
  "description" : "レセプト電算用修飾語マスター コードシステム",
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
  "copyright" : "Copyright 社会保険診療報酬支払基金",
  "caseSensitive" : true,
  "content" : "fragment"
}

```
