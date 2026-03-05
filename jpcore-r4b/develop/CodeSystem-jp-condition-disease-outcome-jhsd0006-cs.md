# JP Core Condition Disease Outcome JHSD0006 CodeSystem - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev-temp

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Condition Disease Outcome JHSD0006 CodeSystem**

## CodeSystem: JP Core Condition Disease Outcome JHSD0006 CodeSystem 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/CodeSystem/JHSD0006
* **項目**: *Version*
  * **内容**: 2.0.0-dev-temp
* **項目**: *Name*
  * **内容**: JP_ConditionDieaseOutcomeJHSD0006_CS
* **項目**: *Title*
  * **内容**: JP Core Condition Disease Outcome JHSD0006 CodeSystem
* **項目**: *Status*
  * **内容**: Active ( 2023-08-05 )
* **項目**: *Copyright*
  * **内容**: Copyright Japanese Association of Healthcare Information Systems Industry(JAHIS) 一般社団法人保健医療福祉情報システム工業会

 
JAHIS病名情報データ交換規約Ver.3.1C JHSD表00006-転帰区分 コードシステム 

 This Code system is referenced in the content logical definition of the following value sets: 

* [JP_ConditionDiseaseOutcomeHL70241_JHSD0006_VS](ValueSet-jp-condition-disease-outcome-hl70241-jhsd0006-vs.md)
* [JP_ConditionDiseaseOutcomeJHSD0006_VS](ValueSet-jp-condition-disease-outcome-jhsd0006-vs.md)

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "jp-condition-disease-outcome-jhsd0006-cs",
  "url" : "http://jpfhir.jp/fhir/core/CodeSystem/JHSD0006",
  "version" : "2.0.0-dev-temp",
  "name" : "JP_ConditionDieaseOutcomeJHSD0006_CS",
  "title" : "JP Core Condition Disease Outcome JHSD0006 CodeSystem",
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
  "description" : "JAHIS病名情報データ交換規約Ver.3.1C JHSD表00006-転帰区分 コードシステム",
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
  "copyright" : "Copyright Japanese  Association of Healthcare Information Systems Industry(JAHIS)  一般社団法人保健医療福祉情報システム工業会",
  "caseSensitive" : true,
  "content" : "complete",
  "count" : 4,
  "concept" : [
    {
      "code" : "I",
      "display" : "中止"
    },
    {
      "code" : "M",
      "display" : "寛解"
    },
    {
      "code" : "C",
      "display" : "継続"
    },
    {
      "code" : "O",
      "display" : "その他"
    }
  ]
}

```
