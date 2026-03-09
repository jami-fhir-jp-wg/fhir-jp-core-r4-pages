# JP Core Physical Exam Code CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Physical Exam Code CodeSystem**

## CodeSystem: JP Core Physical Exam Code CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_PhysicalExamCode_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_PhysicalExamCode_CS
* **項目**: *Title*
  * **内容**: JP Core Physical Exam Code CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-10-31 )
* **項目**: *Copyright*
  * **内容**: Copyright FHIR Japanese implementation research working group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会NeXEHRS課題研究会FHIR日本実装検討WG

 
身体所見の区分を表すコード 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_PhysicalExamCode_VS](ValueSet-jp-physicalexamcode-vs.md)

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-physicalexamcode-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_PhysicalExamCode_CS",
  "version" : "2.0.0-dev",
  "name" : "JP_PhysicalExamCode_CS",
  "title" : "JP Core Physical Exam Code CodeSystem",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-10-31",
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
  "description" : "身体所見の区分を表すコード",
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
  "copyright" : "Copyright FHIR Japanese implementation research working group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会NeXEHRS課題研究会FHIR日本実装検討WG",
  "caseSensitive" : true,
  "valueSet" : "http://jpfhir.jp/fhir/core/ValueSet/JP_PhysicalExamCode_VS",
  "content" : "complete",
  "count" : 2,
  "concept" : [
    {
      "code" : "physical-findings",
      "display" : "Physical Findings"
    },
    {
      "code" : "detailed-physical-findings",
      "display" : "Detailed Physical Findings"
    }
  ]
}

```
