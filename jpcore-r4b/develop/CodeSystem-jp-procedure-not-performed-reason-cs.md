# JP Core Procedure Not Performed Reason CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev-temp

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Procedure Not Performed Reason CodeSystem**

## CodeSystem: JP Core Procedure Not Performed Reason CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_ProcedureNotPerformedReason_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev-temp
* **項目**: *Name*
  * **内容**: JP_ProcedureNotPerformedReason_CS
* **項目**: *Title*
  * **内容**: JP Core Procedure Not Performed Reason CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-10-31 )
* **項目**: *Copyright*
  * **内容**: Copyright FHIR Japanese implementation research working group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会NeXEHRS課題研究会FHIR日本実装検討WG

 
処置が実施されなかった理由、または開始された処置が完了しなかった理由を示すコード（より適切なコードと用語に見直し必要） 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ProcedureNotPerformedReason_VS](ValueSet-jp-procedure-not-performed-reason-vs.md)

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-procedure-not-performed-reason-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_ProcedureNotPerformedReason_CS",
  "version" : "2.0.0-dev-temp",
  "name" : "JP_ProcedureNotPerformedReason_CS",
  "title" : "JP Core Procedure Not Performed Reason CodeSystem",
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
  "description" : "処置が実施されなかった理由、または開始された処置が完了しなかった理由を示すコード（より適切なコードと用語に見直し必要）",
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
  "valueSet" : "http://jpfhir.jp/fhir/core/ValueSet/JP_ProcedureNotPerformedReason_VS",
  "content" : "complete",
  "count" : 5,
  "concept" : [
    {
      "code" : "JPPNPR001",
      "display" : "処置が禁忌"
    },
    {
      "code" : "JPPNPR002",
      "display" : "処置が適応外"
    },
    {
      "code" : "JPPNPR003",
      "display" : "処置を拒否、または望まず"
    },
    {
      "code" : "JPPNPR004",
      "display" : "処置が継続困難"
    },
    {
      "code" : "JPPNPR005",
      "display" : "処置が実施困難"
    }
  ]
}

```
