# JP Core Procedure Performer Role ValueSet - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Procedure Performer Role ValueSet**

## ValueSet: JP Core Procedure Performer Role ValueSet 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/ValueSet/JP_ProcedurePerformerRole_VS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ProcedurePerformerRole_VS
* **項目**: *Title*
  * **内容**: JP Core Procedure Performer Role ValueSet
* **項目**: *Status*
  * **内容**: Active ( 2023-10-31 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
処置を実施した者の役割（ロール）を示す値セット 

 **References** 

* [JP Core Procedure Profile](StructureDefinition-jp-procedure.md)

### Logical Definition (CLD)

* Include all codes defined in [`http://jpfhir.jp/fhir/core/CodeSystem/JP_PractitionerRole_CS`](https://simplifier.net/resolve?scope=jpfhir-terminology@1.4.0&canonical=http://jpfhir.jp/fhir/core/CodeSystem/JP_PractitionerRole_CS)version 📦1.1.1

 

### Expansion

-------

 Explanation of the columns that may appear on this page: 

| | |
| :--- | :--- |
| Level | A few code lists that FHIR defines are hierarchical - each code is assigned a level. In this scheme, some codes are under other codes, and imply that the code they are under also applies |
| System | The source of the definition of the code (when the value set draws in codes defined elsewhere) |
| Code | The code (used as the code in the resource instance) |
| Display | The display (used in the*display*element of a[Coding](http://hl7.org/fhir/R4B/datatypes.html#Coding)). If there is no display, implementers should not simply display the code, but map the concept into their application |
| Definition | An explanation of the meaning of the concept |
| Comments | Additional notes about how to use the code |

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "jp-procedure-performer-role-vs",
  "url" : "http://jpfhir.jp/fhir/core/ValueSet/JP_ProcedurePerformerRole_VS",
  "version" : "2.0.0-dev",
  "name" : "JP_ProcedurePerformerRole_VS",
  "title" : "JP Core Procedure Performer Role ValueSet",
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
  "description" : "処置を実施した者の役割（ロール）を示す値セット",
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
  "compose" : {
    "include" : [
      {
        "system" : "http://jpfhir.jp/fhir/core/CodeSystem/JP_PractitionerRole_CS"
      }
    ]
  }
}

```
