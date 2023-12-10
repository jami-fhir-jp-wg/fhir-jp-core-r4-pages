ここで扱っているTransactionの多くは、患者の医療や健康に関する重要な情報を扱っている。データの扱いに方によっては、情報流出リスクを伴い、社会的な信頼を失うことも想定される。すべてのTransactionは、適切なアクセス権限の設定やサービスの公開方法、データの暗号化等を実施した上で、データを保護する必要がある。  
本対象は、健康医療データを扱う機関であり、医療福祉施設およびサービス・システム提供業者の両方に当てはまる。 ここで記載されている内容は最低限考慮すべき事項であって、実装にあっては分析を行った上でより環境に応じて適切ルールを策定すること。規約等は更新されている場合があるため、検討する際には最新ものであることを確認すること。

### FHIR BASE Securityへの考慮
---
実装者はFHIR BASEにある[FHIR Security](https://hl7.org/fhir/R4B/security.html)に規定にされている下記の項目に対して考慮し、要求項目には対応しなければならない (**SHALL**)。
- [Communications](https://hl7.org/fhir/R4B/security.html#http)
- [Authentication](https://hl7.org/fhir/R4B/security.html#authentication)
- [Authorization/Access Control](https://hl7.org/fhir/R4B/security.html#authorization/access%20control)
- [Audit Logging](https://hl7.org/fhir/R4B/security.html#audit%20logging)
- [Digital Signatures](https://hl7.org/fhir/R4B/security.html#digital%20signatures)
- [Security Labels](https://hl7.org/fhir/R4B/security-labels.html)
- [Narrative](https://hl7.org/fhir/R4B/security.html#narrative)

### JP CoreにおけるSecurity要件
---
#### 全般
- 対象となる施設は、厚生労働省の定める「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」企画管理編6章に従ってリスクマネジメントを実施すること (**SHALL**)   
　委託する事業者 を選定する場合には、**JIS Q 15001**、**JIS Q 27001** 又は これと同等の規格の認証を受けているシステム関連事業者を選定すること（「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」経営管理編5.1②）(**SHALL**)。なお、これらの認証は、対象事業者が適切な体制を整備していることを示すものであり、あくまで事業者として最低限の適格性を医療機関等へ示す手段として捉えている。（「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」Q&A企Q-27）  
　委託した医療情報システム等の安全管理の妥当性については、対象事業者が、医療情報システム等の安全管理に係る評価を行い、 その評価結果の情報提供を受けること(**SHALL**)。このとき、医療情報システム等関連業務に関与する担当者自らが 評価を行うと、信頼性及び客観性が低下するため、対象事業者内部の独立した監査部門や第三者機関が評価を行うことが望ましい。（「[医療情報を取扱う情報システム・サービス提供事業者における安全管理ガイドライン][医療情報システム・サービス提供事業者安全管理ガイドラインURL]」第1版4.3）を医療機関側の立場からの表現に修正(**SHOULD**)  
　また、厚生労働省ガイドライン第6.0版企画管理編6章ではリスク評価までを記述しているが、リスク対応、残存リスクへの合意形成を図ること（医療情報を取扱う情報システム・サービス提供事業者における安全管理ガイドライン５章）(**SHALL**)
- セキュリティ監査にて正確な時刻を確立するためにタイムサーバを利用すること (**SHOULD**)、タイムサーバは独立行政法人 情報通信研究機構(NICT)もしくはそこから派生するタイムサーバを利用することが望ましい (**SHOULD**)
- サーバの配置に際しては日本ネットワークセキュリティ協会(JNSA)の定める「[サーバールームに関する標準][サーバールームに関する標準URL]」を参考にし堅牢な環境を用意することが望ましい (**SHOULD**)
- システムで利用するOSやサーバソフトウエア、ミドルウエアに関するセキュリティリスクを注視し、必要によって適宜バージョンアップしなければならない (**SHALL**)
- 監査証跡ログを採取し、特に個人情報の流出防止の観点より認証、個人情報へのアクセス、印刷およびデータエクスポートをするイベントは注意深く監視し不正利用等が発生していないかを確認すること (**SHOULD**)、「[JAHISヘルスケア分野における監査証跡のメッセージ標準規約Ver.2.1][JAHISヘルスケア分野監査証跡のメッセージ標準規約Ver.2.1URL]」を参考にすること。

- ネットワークのセキュリティに関しては「[医療情報システムの安全管理に関するガイドライン第6.0版][[医療情報システム安全管理ガイドライン第6.0版URL]]」システム運用編13章に準拠すること(**SHALL**)  
　5.2版6.11C項対応したシステム運用編7章④⑭、7.2.1章、10.1章、18.1章、企画管理編14章②、15章⑦、2章①、12章⑤、８章⑧にも準拠すること(**SHALL**)
特にREST API等API連携のセキュリティ確保のため、外部からの攻撃や意図せぬアクセス を防止できるように、必要に応じてネットワークセキュリティを確保し、API連携により利用するユ ーザ・アプリケーションやデバイスの範囲を限定し、その責任分界とアクセスポリシーやログ管理を 明確にした上で、それに沿った認証・認可に関する仕組みを設ける必要がある(**SHOULD**)（「[医療情報システムの安全管理に関するガイドライン第6.0版][JAHISヘルスケア分野監査証跡のメッセージ標準規約Ver.2.1URL]」システム運用編14.1.2章）  
　またネットワーク上からの不正アクセスや不正ソフトウェア対策としてリスク分析による費用対効果を考慮した上で、IDS、IPS、EDRや「振る舞い検知」などの対策の検討が必要である (**SHOULD**)（「[医療情報システムの安全管理に関するガイドライン第6.0版][JAHISヘルスケア分野監査証跡のメッセージ標準規約Ver.2.1URL]」システム運用編 13.2章)。  
- 法令で署名又は記名・押印が義務付けられた文書において記名・押印を電子署名に代える場合、以下の条件を満たす電子署名を行う必要がある (**SHALL**)
1.	以下の電子証明書を用いて電子署名を施すこと  
（「[医療情報システムの安全管理に関するガイドライン第6.0版][JAHISヘルスケア分野監査証跡のメッセージ標準規約Ver.2.1URL]」企画管理編の14章①１）　　
「電子署名及び認証業務に関する法律」（平成 12 年法律第 102 号）第２条第１項に規定する 電子署名を施すこと。なおこれはローカル署名のほか、リモート署名、立会人型電子署名の場合も同様である

- 法令で医師等の国家資格を有する者による作成が求められている文書については、以下の（ a～ c ）のいずれかにより、医師等の国家資格の確認が電子的に検証できる電子署名等 を用いること。  
(a) 厚生労働省の定める準拠性監査基準を満たす保健医療福祉分野 PKI 認証局の発行する電子証明書を用いて電子署名を施すこと 。  
(b) 認定認証事業者（電子署名法第 2 条第 3 項に定める特定認証業務を行う者として主務大臣の認定を受けた者をいう。 以下同じ。）又は認証事業者（電子署名法第 2 条第 2 項の認証業務を行う者（認定認証事業者を除く。）をいう。）の発行する電子証明書を用いて電子署名を施すこと。その場合、当該電子署名を施された文書を受け取る者が、医師等の国家資格の確認を電子的に検証でき、電子署名の検証を正しくできることが必要である。  
(c) 「電子署名等に係る地方公共団体情報システム機構の認証業務に関する法律」平成 14 年法律第 153 号）に基づき、平成 16 年 1 月 29 日 から開始されている公的個人認証サービスを用いることも可能であるが、その場合、その 署名用電子証明書に係る 電子署名に紐づく医師等の国家資格が検証時に電子的に確認できること、当該電子署名を施された文書を受け取る者が公的個人認証サービスを用いた電子署名を検証できることが必要である。

1.	法定保存期間等の必要な期間、電子署名の検証を継続して実施できるよう、必要に応じて電子署名を含む文書全体にタイムスタンプを付与すること
（「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」企画管理編14章①2）

#### クラウドでの利用
- 「外部保存改正通知」で定められた文書等をクラウドに保管する場合は、厚生労働省の定める「「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」企画管理編７章の該当項目（⑤、⑦～⑩）に対して準拠しなければならない (**SHALL**)
- 利用するクラウドサービスの選定については、少なくとも「[医療情報システムの安全管理に関するガイドライン第6.0版][医療情報システム安全管理ガイドライン第6.0版URL]」企画管理編」第7章⑥に掲げる事項を確認すること。 (**SHALL**)

{% include external-link-reference.md %}