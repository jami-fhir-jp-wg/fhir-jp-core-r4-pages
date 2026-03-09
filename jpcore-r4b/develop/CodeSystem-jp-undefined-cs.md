# JP Core Undefined CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Undefined CodeSystem**

## CodeSystem: JP Core Undefined CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_Undefined_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_Undefined_CS
* **項目**: *Title*
  * **内容**: JP Core Undefined CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-10-31 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
未定義のコードシステム。使用する予定のコードシステムが利用できない場合や方針未決定の場合等に割り振る特別なリソースである。 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ProcedureCodesICHI_VS](ValueSet-jp-procedure-codes-ichi-vs.md)
* [JP_ProcedureCondition_VS](ValueSet-jp-procedure-condition-vs.md)
* [JP_ProcedureDeviceAction_VS](ValueSet-jp-procedure-device-action-vs.md)
* [JP_ProcedureDeviceKind_VS](ValueSet-jp-procedure-devicekind-vs.md)
* [JP_ProcedureFollowUp_VS](ValueSet-jp-procedure-followup-vs.md)
* [JP_ProcedureReason_VS](ValueSet-jp-procedure-reason-vs.md)
* [JP_Undefined_VS](ValueSet-jp-undefined-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-undefined-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_Undefined_CS",
  "version" : "2.0.0-dev",
  "name" : "JP_Undefined_CS",
  "title" : "JP Core Undefined CodeSystem",
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
  "description" : "未定義のコードシステム。使用する予定のコードシステムが利用できない場合や方針未決定の場合等に割り振る特別なリソースである。",
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
  "caseSensitive" : true,
  "content" : "fragment"
}

```
