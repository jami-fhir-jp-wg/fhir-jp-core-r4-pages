# JP Core Condition Disease Outcome HL70241 ValueSet - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Outcome HL70241 ValueSet**

## ValueSet: JP Core Condition Disease Outcome HL70241 ValueSet 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/ValueSet/JP_ConditionDiseaseOutcomeHL70241_VS
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_ConditionDiseaseOutcomeHL70241_VS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Outcome HL70241 ValueSet
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: copyright HL7 Japan (出典：HL7-0241)

 
HL7表0241の病名転帰区分を示す値セット 

 **References** 

* [JP Core Disease Outcome Extension](StructureDefinition-jp-condition-disease-outcome.md)

### Logical Definition (CLD)

* Include all codes defined in [`http://jpfhir.jp/fhir/core/CodeSystem/HL70241`](CodeSystem-jp-condition-disease-outcome-hl70241-cs.md)version 📦2.0.0-dev

 

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
  "id" : "jp-condition-disease-outcome-hl70241-vs",
  "url" : "http://jpfhir.jp/fhir/core/ValueSet/JP_ConditionDiseaseOutcomeHL70241_VS",
  "version" : "2.0.0-dev",
  "name" : "JP_ConditionDiseaseOutcomeHL70241_VS",
  "title" : "JP Core Condition Disease Outcome HL70241 ValueSet",
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
  "description" : "HL7表0241の病名転帰区分を示す値セット",
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
  "copyright" : "copyright HL7 Japan (出典：HL7-0241)",
  "compose" : {
    "include" : [
      {
        "system" : "http://jpfhir.jp/fhir/core/CodeSystem/HL70241"
      }
    ]
  }
}

```
