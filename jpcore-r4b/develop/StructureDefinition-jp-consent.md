# JP Core Consent Profile - HL7 FHIR JP Core ImplementationGuide v2.0.0-dev

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **JP Core Consent Profile**

## Resource Profile: JP Core Consent Profile 

* **項目**: *定義URL*
  * **内容**: http://jpfhir.jp/fhir/core/StructureDefinition/JP_Consent
* **項目**: *Version*
  * **内容**: 2.0.0-dev
* **項目**: *Name*
  * **内容**: JP_Consent
* **項目**: *Title*
  * **内容**: JP Core Consent Profile
* **項目**: *Status*
  * **内容**: Draft ( 2023-10-20 )
* **項目**: *Copyright*
  * **内容**: Copyright Japan FHIR Implementation Infrastructure Study Group in Japan Association of Medical Informatics (JAMI) 一般社団法人日本医療情報学会FHIR国内実装基盤研究会

 
Detailed Descriptions for the elements in the Consent resource. 

本プロファイルは、患者のアレルギー不耐症とその臨床的な評価を表現するJP_Consentリソースの記録・更新・検索を行う上で、準拠するべき必須となる要素や、サポートすべき拡張、用語、検索パラメータを定義する。

## 6.2.1 Scope and Usage

The purpose of this Resource is to be used to express a Consent regarding Healthcare. There are four anticipated uses for the Consent Resource, all of which are written or verbal agreements by a healthcare consumer [grantor] or a personal representative, made to an authorized entity [grantee] concerning authorized or restricted actions with any limitations on purpose of use, and handling instructions to which the authorized entity must comply:

Privacy Consent Directive: Agreement to collect, access, use or disclose (share) information. Medical Treatment Consent Directive: Consent to undergo a specific treatment (or record of refusal to consent). Research Consent Directive: Consent to participate in research protocol and information sharing required. Advance Care Directives: Consent to instructions for potentially needed medical treatment (e.g. DNR). This resource is scoped to cover all four uses, but at this time, only the privacy use case is modeled. The scope of the resource may change when the other possible scopes are investigated, tested, or profiled.

A FHIR Consent Directive instance is considered the encoded legally binding Consent Directive if it meets requirements of a policy domain requirements for an enforceable contract. In some domains, electronic signatures of one or both of the parties to the content of an encoded representation of a Consent Form is deemed to constitute a legally binding Consent Directive. Some domains accept a notary’s electronic signature over the wet or electronic signature of a party to the Consent Directive as the additional identity proofing required to make an encoded Consent Directive legally binding. Other domains may only accept a wet signature or might not require the parties’ signatures at all.

Whatever the criteria are for making an encoded FHIR Consent Directive legally binding, anything less than a legally binding representation of a Consent Directive must be identified as such, i.e., as a derivative of the legally binding Consent Directive, which has specific usage in Consent Directive workflow management.

このリソースの目的は、ヘルスケアに関する同意を表明するために使用することです。このリソースには4つの用途が想定されており、それらはすべて、医療利用者（付与者）または個人的な代理人が、権限を付与された団体（被付与者）に対して行う許可された行為または制限された行為に関する書面または口頭による同意です。その使用目的には制限があり、権限を付与された団体が従わなければならない取扱いの指示があります：

1. プライバシー同意指令：情報の収集、アクセス、使用、開示（共有）に関する同意、制限、禁止。
1. 医療同意指令：特定の治療を受けることへの同意、または同意拒否の記録。
1. 研究同意指令：研究プロトコルへの参加と情報共有の同意。
1. 事前ケア指示書（Advance Care Directives）：潜在的に必要とされる医療処置（DNRなど）の指示に対する同意。

このリソースは4つの用途をすべてカバーするようにスコープされていますが、現時点ではプライバシーのユースケースのみがモデル化されています。このリソースのスコープは、他の可能なスコープが調査、テスト、またはプロファイリングされたときに変更されるかもしれません。

FHIR同意指示書インスタンスは、それが強制可能な契約に関するポリシードメインの要件を満たす場合、符号化された法的拘束力のある同意指示書とみなされます。ドメインによっては、エンコードされた「同意書」の表現内容に対する当事者の一方または双方の電子署名が、法的拘束力のある「同意の指示」を構成するとみなされます。ドメインによっては、エンコードされた同意指令に法的拘束力を持たせるために必要な追加的な身元証明として、同意指令の当事者のウェット署名または電子署名の上に公証人の電子署名を認めることもあります。他のドメインでは、湿式の署名しか受け付けないか、当事者の署名を全く必要としない場合もあります。

エンコードされたFHIR同意指示書に法的拘束力を持たせるための基準が何であれ、同意指示書の法的拘束力のない表現は、そのようなもの、すなわち、同意指示書のワークフロー管理における特定の用法がある法的拘束力のある同意指示書の派生物として識別されなければなりません。

## 6.2.1.1 Privacy Consent Directive (PCD)

Privacy policies define how Individually Identifiable Health Information (IIHI) is to be collected, accessed, used and disclosed. A Privacy Consent Directive as a legal record of a patient's (e.g. a healthcare consumer) agreement with a party responsible for enforcing the patient's choices, which permits or denies identified actors or roles to perform actions affecting the patient within a given context for specific purposes and periods of time. All consent directives have a policy context, which is any set of organizational or jurisdictional policies which may limit the consumer’s policy choices, and which include a named range of actions allowed. In addition, Privacy Consent Directives provide the ability for a healthcare consumer to delegate authority to a Substitute Decision Maker who may act on behalf of that individual. Alternatively, a consumer may author/publish their privacy preferences as a self-declared Privacy Consent Directive.

The Consent resource on FHIR provides support for alternative representations for expressing interoperable health information privacy consent directives in a standard form for the exchange and enforcement by sending, intermediating, or receiving systems of privacy policies that can be enforced by consuming systems (e.g., scanned documents, of computable structured entries elements, FHIR structures with optional attached, or referenced unstructured representations.) It may be used to represent the Privacy Consent Directive itself, a Consent Statement, which electronically represents a Consent Directive, or Consent Metadata, which is the minimum necessary consent content derived from a Consent Directive for use in workflow management.

プライバシーポリシーは、個人を特定できる健康情報（IIHI）の収集、アクセス、使用、開示の方法を定義します。プライバシー同意指令とは、患者（例えば医療消費者）が、患者の選択を強制する責任を負う当事者と合意した法的記録であり、特定された行為者又は役割が、特定の目的及び期間において、特定された文脈の中で患者に影響を及ぼす行為を許可又は拒否するものです。すべての同意指令は、消費者の方針の選択を制限する可能性があり、許可される行為の範囲を含む、組織又は管轄区域の方針の集合であり、方針の文脈を持っています。さらに、プライバシー同意指示書は、医療利用者が代理決定者に権限を委譲することができるか、あるいは医療利用者が自己宣言したプライバシー同意指示書として、自分のプライバシー嗜好を作成／公表することもできます。

FHIRのConsentリソースは、相互運用可能な医療情報のプライバシー同意指令を標準的な形式で表現するための代替表現をサポートします。これは、プライバシー同意指令そのもの、同意指令を電子的に表現する同意声明、ワークフロー管理で使用するために同意指令から導き出された必要最小限の同意内容である同意メタデータを表現するために使用できます。

## 6.2.2 Boundaries and Relationships

Consent management - particularly privacy consent - is complicated by the fact that consent to share is often itself necessary to protect. The need to protect the privacy of the privacy statement itself competes with the execution of the consent statement. For this reason, it is common to deal with 'consent statements' that are only partial representations of the full consent statement that the patient provided.

For this reason, the consent resource contains two elements that refer back to the source: a master identifier, and a direct reference to content from which this Consent Statement was derived. That reference can be one of several things:

* A reference to another consent resource from which this limited statement was derived
* A reference to a document format for the original source (e.g. PDF or CDA - see the HL7 CDAR2 ConsentDirective Implementation Guide , which incorporated the IHE Basic Patient Privacy Consents (BPPC) ), either directly, or in a reference
* The source can be included in the consent as an attachment

The consent statements represent a chain that refers back to the original source consent directive. Applications may be able to follow the chain back to the source but should not generally assume that they are authorized to do this.

Consent Directives are executed by verbal acknowledge or by being signed - either on paper, or digitally. Consent Signatures will be found in the Provenance resource (example consent and signature). Implementation Guides will generally make rules about what signatures are required, and how they are to be shared and used.

同意の管理、特にプライバシーの同意は、共有への同意自体がしばしば保護が必要とされるという事実によって複雑になっています。プライバシーを保護する必要性そのものが、同意声明の実行と競合することがあります。そのため、患者が提供した完全な同意声明の部分的な表現である「同意声明」を扱うことが一般的です。

このため、同意リソースには2つの要素、すなわちマスター識別子と、この同意文が由来するコンテンツへの直接参照が含まれています。この参照は、いくつかのものの中で一つであり、以下のようなものが考えられます：

* この限定されたステートメントが派生した別の同意リソースへの参照
* 元のソースの文書フォーマットへの参照（例えば PDF や CDA - IHE 基本患者プライバシー同意書（BPPC）を組み込んだ HL7 CDAR2 ConsentDirective Implementation Guide を参照）。
* ソースは添付ファイルとして同意書に含めることもできます。

同意文は、元のソース同意指令を参照する連鎖を表しています。アプリケーションはソースまで遡って連鎖をたどることができるかもしれませんが、一般的にはこれを行う権限があると仮定すべきではありません。

同意の指示は、口頭による承認、または署名によって実行されます。同意の署名は、プロベナンストリソース（同意と署名の例）に記載されています。実施要項は一般に、どのような署名が必要で、どのように共有され、使用されるかについて規定します。

## 6.2.3 Background and Context

Change to "The Consent resource is structured with a base policy (represented as Consent.policy/Consent.policyRule) which is either opt-in or opt-out, followed by a listing of exceptions to that policy (represented as Consent.provision(s)). The exceptions can be additional positive or negative exceptions upon the base policy. The set of exceptions include a list of data objects, list of authors, list of recipients, list of Organizations, list of purposeOfUse, and Date Range.

The enforcement of the Privacy Consent Directive is not included but is expected that enforcement can be done using a mix of the various Access Control enforcement methodologies (e.g. OAuth, UMA, XACML). This enforcement includes the details of the enforcement meaning of the elements of the Privacy Consent Directive, such as the rules in place when there is an opt-in consent would be specific about which organizational roles have access to what kinds of resources (e.g. RBAC, ABAC). The specification of these details is not in scope for the Consent resource.

Consentリソースは、オプトインまたはオプトアウトの基本ポリシー（Consent.policy/Consent.policyRule）と、そのポリシーに対する例外のリスト（Consent.provision(s)）で構成されています。例外は、基本ポリシーに対する追加的な肯定的または否定的な例外とすることができます。例外のリストには、データオブジェクトのリスト、作成者のリスト、受信者のリスト、Organizationsのリスト、purposeOfUseのリスト、およびDate Rangeが含まれます。

プライバシー同意指令の施行は含まれていませんが、様々なアクセス制御施行方法論（OAuth、UMA、XACMLなど）を組み合わせて施行することが期待されています。この実施には、プライバシー同意指令の要素の実施意味の詳細が含まれます。例えば、オプトインによる同意がある場合のルールは、どの組織の役割がどのような種類のリソースにアクセスできるのか（例えば、RBAC、ABAC）を具体的に示すものであり、このような詳細は「同意」リソースの範囲外です。

## プロファイル定義

**Usages:**

* Refer to this Profile: [JP Core Consent Profile](StructureDefinition-jp-consent.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/jpfhir.jp.core|current/StructureDefinition/jp-consent)

### プロファイル詳細

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-jp-consent.csv), [Excel](StructureDefinition-jp-consent.xlsx), [Schematron](StructureDefinition-jp-consent.sch) 

### 必須要素

本プロファイルに準拠するためには、次の項目の値が存在しなければならない。

* patient : 本リソースを所有する患者

### Extensions定義

## 利用方法

### OperationおよびSearch Parameter 一覧

#### Search Parameter一覧

##### 必須検索パラメータ

##### 推奨検索パラメータ

##### 追加検索パラメータ

##### オプション検索パラメータ

#### サンプル

## 注意事項

本実装ガイドへのご質問・ご指摘については、
[GitHub Issue](https://github.com/jami-fhir-jp-wg/jp-core-v1x/issues)および
[GitHub PullRequest](https://github.com/jami-fhir-jp-wg/jp-core-v1x/pulls)にて受け付けている。

## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "jp-consent",
  "url" : "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Consent",
  "version" : "2.0.0-dev",
  "name" : "JP_Consent",
  "title" : "JP Core Consent Profile",
  "status" : "draft",
  "date" : "2023-10-20",
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
  "description" : "Detailed Descriptions for the elements in the Consent resource.",
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
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
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
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Consent",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Consent",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Consent",
        "path" : "Consent",
        "short" : "A healthcare consumer's or third party's choices to permit or deny recipients or roles to perform actions for specific purposes and periods of time",
        "definition" : "A record of a healthcare consumer’s choices or choices made on their behalf by a third party, which permits or denies identified recipient(s) or recipient role(s) to perform one or more actions within a given policy context, for specific purposes and periods of time."
      },
      {
        "id" : "Consent.status",
        "path" : "Consent.status",
        "short" : "draft | proposed | active | rejected | inactive | entered-in-error",
        "definition" : "Indicates the current state of this consent."
      },
      {
        "id" : "Consent.scope",
        "path" : "Consent.scope",
        "short" : "Which of the four areas this resource covers (extensible)",
        "definition" : "A selector of the type of consent being presented: ADR, Privacy, Treatment, Research. This list is now extensible.",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/ValueSet/consent-scope"
        }
      },
      {
        "id" : "Consent.category",
        "path" : "Consent.category",
        "short" : "Classification of the consent statement - for indexing/retrieval",
        "definition" : "A classification of the type of consents found in the statement. This element supports indexing and retrieval of consent statements.",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/ValueSet/consent-category"
        }
      },
      {
        "id" : "Consent.patient",
        "path" : "Consent.patient",
        "short" : "Who the consent applies to",
        "definition" : "The patient/healthcare consumer to whom this consent applies.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : ["http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient"]
          }
        ]
      },
      {
        "id" : "Consent.performer",
        "path" : "Consent.performer",
        "short" : "Who is agreeing to the policy and rules",
        "definition" : "Either the Grantor, which is the entity responsible for granting the rights listed in a Consent Directive or the Grantee, which is the entity responsible for complying with the Consent Directive, including any obligations or limitations on authorizations and enforcement of prohibitions.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Practitioner",
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_PractitionerRole"
            ]
          }
        ]
      },
      {
        "id" : "Consent.organization",
        "path" : "Consent.organization",
        "short" : "Custodian of the consent",
        "definition" : "The organization that manages the consent, and the framework within which it is executed.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization"
            ]
          }
        ]
      },
      {
        "id" : "Consent.source[x]",
        "path" : "Consent.source[x]",
        "short" : "Source from which this consent is taken",
        "definition" : "The source on which this consent statement is based. The source might be a scanned original paper form, or a reference to a consent that links back to such a source, a reference to a document repository (e.g. XDS) that stores the original consent document.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Consent",
              "http://hl7.org/fhir/StructureDefinition/DocumentReference",
              "http://hl7.org/fhir/StructureDefinition/Contract",
              "http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse"
            ]
          }
        ]
      },
      {
        "id" : "Consent.verification",
        "path" : "Consent.verification",
        "short" : "Has the instruction been verified",
        "definition" : "Whether the instruction is verified."
      },
      {
        "id" : "Consent.verification.verifiedWith",
        "path" : "Consent.verification.verifiedWith",
        "short" : "Person who verified",
        "definition" : "Who verified the instruction (Patient, Relative or other Authorized Person).",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient",
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson"
            ]
          }
        ]
      },
      {
        "id" : "Consent.provision",
        "path" : "Consent.provision",
        "short" : "Constraints to the base Consent.policyRule",
        "definition" : "An exception to the base policy of this consent. An exception can be an addition or removal of access permissions."
      },
      {
        "id" : "Consent.provision.type",
        "path" : "Consent.provision.type",
        "short" : "deny | permit",
        "definition" : "Action stipulated by this rule. The type can be 'permit' or 'deny' to determine if the rule allows or prohibits the specified operations."
      },
      {
        "id" : "Consent.provision.period",
        "path" : "Consent.provision.period",
        "short" : "Timeframe for this rule",
        "definition" : "The timeframe in which the data is controlled by this provision."
      },
      {
        "id" : "Consent.provision.actor",
        "path" : "Consent.provision.actor",
        "short" : "Who the rule applies to",
        "definition" : "Who the consent provision rule applies to."
      },
      {
        "id" : "Consent.provision.actor.role",
        "path" : "Consent.provision.actor.role",
        "short" : "Role using the content",
        "definition" : "How the individual is involved in the resources content that is described in the exception.",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/ValueSet/security-role-type"
        }
      },
      {
        "id" : "Consent.provision.actor.reference",
        "path" : "Consent.provision.actor.reference",
        "short" : "Reference to the actor",
        "definition" : "The resource that identifies the actor. For example, a patient, practitioner, or organization.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/StructureDefinition/Device",
              "http://hl7.org/fhir/StructureDefinition/Group",
              "http://hl7.org/fhir/StructureDefinition/CareTeam",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Organization",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Patient",
              "http://jpfhir.jp/fhir/core/StructureDefinition/JP_Practitioner",
              "http://hl7.org/fhir/StructureDefinition/RelatedPerson",
              "http://hl7.org/fhir/StructureDefinition/PractitionerRole"
            ]
          }
        ]
      },
      {
        "id" : "Consent.provision.action",
        "path" : "Consent.provision.action",
        "short" : "Actions controlled by this rule",
        "definition" : "A list of actions controlled by this rule, which are controlled by this provision."
      },
      {
        "id" : "Consent.provision.class",
        "path" : "Consent.provision.class",
        "short" : "e.g. Read, Update, Delete",
        "definition" : "Actions controlled by this provision."
      },
      {
        "id" : "Consent.provision.code",
        "path" : "Consent.provision.code",
        "short" : "e.g. Read, Update, Delete",
        "definition" : "If this code is found in an instance, then the rule applies.",
        "binding" : {
          "strength" : "example",
          "valueSet" : "http://hl7.org/fhir/ValueSet/consent-content-code"
        }
      },
      {
        "id" : "Consent.provision.dataPeriod",
        "path" : "Consent.provision.dataPeriod",
        "short" : "Timeframe for data controlled by this rule",
        "definition" : "The timeframe for data controlled by this provision."
      },
      {
        "id" : "Consent.provision.data",
        "path" : "Consent.provision.data",
        "short" : "Data controlled by this rule",
        "definition" : "The resources controlled by this rule, if specific resources are referenced."
      }
    ]
  }
}

```
