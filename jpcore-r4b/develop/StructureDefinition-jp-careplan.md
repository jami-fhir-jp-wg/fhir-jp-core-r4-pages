# JP Core CarePlan Profile - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev-temp

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core CarePlan Profile**

## Resource Profile: JP Core CarePlan Profile 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/StructureDefinition/JP_CarePlan
* **項目**: *Version*
  * **内容**: 2.0.0-dev-temp
* **項目**: *Name*
  * **内容**: JP_CarePlan
* **項目**: *Title*
  * **内容**: JP Core CarePlan Profile
* **項目**: *Status*
  * **内容**: Draft ( 2022-10-24 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
このプロファイルはJP Core CarePlanリソースに対する共通の制約と拡張を定めたものである。 

**Usages:**

* Refer to this Profile: [JP Core CarePlan Profile](StructureDefinition-jp-careplan.md), [JP Core MedicationRequest Injection Profile](StructureDefinition-jp-medicationrequest-injection.md) and [JP Core MedicationRequest Profile](StructureDefinition-jp-medicationrequest.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/jpfhir.jp.core|current/StructureDefinition/jp-careplan)

### プロファイル詳細

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-jp-careplan.csv), [Excel](StructureDefinition-jp-careplan.xlsx), [Schematron](StructureDefinition-jp-careplan.sch) 

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "jp-careplan",
  "url" : "http://jpfhir.jp/fhir/core/StructureDefinition/JP_CarePlan",
  "version" : "2.0.0-dev-temp",
  "name" : "JP_CarePlan",
  "title" : "JP Core CarePlan Profile",
  "status" : "draft",
  "date" : "2022-10-24",
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
  "description" : "このプロファイルはJP Core CarePlanリソースに対する共通の制約と拡張を定めたものである。",
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
  "fhirVersion" : "4.3.0",
  "mapping" : [
    {
      "identity" : "workflow",
      "uri" : "http://hl7.org/fhir/workflow",
      "name" : "Workflow Pattern"
    },
    {
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
    },
    {
      "identity" : "w5",
      "uri" : "http://hl7.org/fhir/fivews",
      "name" : "FiveWs Pattern Mapping"
    },
    {
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "CarePlan",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/CarePlan",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "CarePlan",
        "path" : "CarePlan"
      },
      {
        "id" : "CarePlan.basedOn",
        "path" : "CarePlan.basedOn",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-hierarchy",
                "valueBoolean" : true
              }
            ],
            "code" : "Reference",
            "targetProfile" : ["http://jpfhir.jp/fhir/core/StructureDefinition/JP_CarePlan"]
          }
        ]
      },
      {
        "id" : "CarePlan.replaces",
        "path" : "CarePlan.replaces",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-hierarchy",
                "valueBoolean" : true
              }
            ],
            "code" : "Reference",
            "targetProfile" : ["http://jpfhir.jp/fhir/core/StructureDefinition/JP_CarePlan"]
          }
        ]
      },
      {
        "id" : "CarePlan.partOf",
        "path" : "CarePlan.partOf",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-hierarchy",
                "valueBoolean" : true
              }
            ],
            "code" : "Reference",
            "targetProfile" : ["http://jpfhir.jp/fhir/core/StructureDefinition/JP_CarePlan"]
          }
        ]
      },
      {
        "id" : "CarePlan.subject",
        "path" : "CarePlan.subject",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : ["http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient"]
          }
        ]
      },
      {
        "id" : "CarePlan.encounter",
        "path" : "CarePlan.encounter",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Encounter"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.author",
        "path" : "CarePlan.author",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/Device",
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson",
              "http://hl7.org/fhir/StructureDefinition/CareTeam",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Practitioner",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_PractitionerRole",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.contributor",
        "path" : "CarePlan.contributor",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/Device",
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson",
              "http://hl7.org/fhir/StructureDefinition/CareTeam",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Practitioner",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_PractitionerRole",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.addresses",
        "path" : "CarePlan.addresses",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Condition"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.activity.reference",
        "path" : "CarePlan.activity.reference",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/Appointment",
              "http://hl7.org/fhir/StructureDefinition/CommunicationRequest",
              "http://hl7.org/fhir/StructureDefinition/DeviceRequest",
              "http://hl7.org/fhir/StructureDefinition/NutritionOrder",
              "http://hl7.org/fhir/StructureDefinition/Task",
              "http://hl7.org/fhir/StructureDefinition/ServiceRequest",
              "http://hl7.org/fhir/StructureDefinition/VisionPrescription",
              "http://hl7.org/fhir/StructureDefinition/RequestGroup",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_MedicationRequest"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.activity.detail.reasonReference",
        "path" : "CarePlan.activity.detail.reasonReference",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/DocumentReference",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Condition",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Observation_Common",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_DiagnosticReport_Common"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.activity.detail.performer",
        "path" : "CarePlan.activity.detail.performer",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson",
              "http://hl7.org/fhir/StructureDefinition/CareTeam",
              "http://hl7.org/fhir/StructureDefinition/HealthcareService",
              "http://hl7.org/fhir/StructureDefinition/Device",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Practitioner",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_PractitionerRole",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient"
            ]
          }
        ]
      },
      {
        "id" : "CarePlan.activity.detail.product[x]",
        "path" : "CarePlan.activity.detail.product[x]",
        "type" : [
          {
            "code" : "CodeableConcept"
          },
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/Substance",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Medication"
            ]
          }
        ]
      }
    ]
  }
}

```
