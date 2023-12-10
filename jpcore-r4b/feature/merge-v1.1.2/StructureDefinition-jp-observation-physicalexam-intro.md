本プロファイル説明は、患者に付属する一項目分の身体所見情報について、情報の登録や検索、取得のために、FHIR Observationリソースを使用するにあたっての、最低限の制約を記述したものである。

Observationリソースに対して本プロファイルに準拠する場合に必須となる要素や、サポートすべき拡張、用語、検索パラメータを定義する。

## 背景および想定シナリオ
本プロファイルは、以下のようなユースケースを想定している。

- Patientリソースから指定された日時、期間での身体所見情報の参照
- Patientリソースから指定された診察方法に対する指定された期間での身体所見情報の参照


## スコープ
Observationはヘルスケアの中心的な要素であり、診断の支援、進捗状況の監視、ベースラインやパターンの決定、さらには人口統計学的特性の把握に使用される。ほとんどのObservationは、いくつかのメタデータを持つ単純な名前/値のペアのアサーションであるが、いくつかのObservationは、他のObservationを論理的にグループ化したり、あるいはマルチコンポーネントのObservationであったりする。

本プロファイルでは上記想定シナリオにて用いられるObservationの用途がスコープであり、患者基本情報の中でも特に身体所見に該当する情報項目の１つを取り扱う際に、必要な要件を定義している。

## プロファイル定義

{% include markdown-link-references.md %}