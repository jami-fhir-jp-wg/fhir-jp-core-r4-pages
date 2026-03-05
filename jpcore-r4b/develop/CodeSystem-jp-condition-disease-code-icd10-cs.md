# JP Core Condition Disease Code ICD-10 CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev-temp

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Code ICD-10 CodeSystem**

## CodeSystem: JP Core Condition Disease Code ICD-10 CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_ConditionDiseaseCodeICD10_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev-temp
* **項目**: *Name*
  * **内容**: JP_ConditionDiseaseCodeICD10_CS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Code ICD-10 CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: Copyright

 
ICD-10 コードシステム 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ConditionDiseaseCodeICD10_VS](ValueSet-jp-condition-disease-code-icd10-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-condition-disease-code-icd10-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_ConditionDiseaseCodeICD10_CS",
  "version" : "2.0.0-dev-temp",
  "name" : "JP_ConditionDiseaseCodeICD10_CS",
  "title" : "JP Core Condition Disease Code ICD-10 CodeSystem",
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
  "description" : "ICD-10 コードシステム",
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
  "copyright" : "Copyright ",
  "caseSensitive" : true,
  "content" : "fragment",
  "concept" : [
    {
      "code" : "K358",
      "display" : "急性化膿性虫垂炎"
    }
  ]
}

```
