# JP Core PlanDefinition ChemotherapyRegimen RegimenType CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core PlanDefinition ChemotherapyRegimen RegimenType CodeSystem**

## CodeSystem: JP Core PlanDefinition ChemotherapyRegimen RegimenType CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JP_ChemotherapyRegimen_RegimenType_CS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ChemotherapyRegimen_RegimenType_CS
* **項目**: *Title*
  * **内容**: JP Core PlanDefinition ChemotherapyRegimen RegimenType CodeSystem
* **項目**: *Status*
  * **内容**: Draft ( 2023-11-30 )
* **項目**: *Copyright*
  * **内容**: Copyright XXX

 
【仮】レジメン種別コード 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ChemotherapyRegimen_RegimenType_VS](ValueSet-jp-chemotherapyregimen-regimentype-vs.md)

このコードシステム は以下のコードを含むフラグメントを提供します:

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-chemotherapyregimen-regimentype-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_ChemotherapyRegimen_RegimenType_CS",
  "version" : "2.0.0-dev",
  "name" : "JP_ChemotherapyRegimen_RegimenType_CS",
  "title" : "JP Core PlanDefinition ChemotherapyRegimen RegimenType CodeSystem",
  "status" : "draft",
  "experimental" : false,
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
  "description" : "【仮】レジメン種別コード",
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
  "copyright" : "Copyright XXX",
  "caseSensitive" : true,
  "content" : "fragment",
  "concept" : [
    {
      "code" : "0001",
      "display" : "aaa"
    },
    {
      "code" : "0002",
      "display" : "bbb"
    }
  ]
}

```
