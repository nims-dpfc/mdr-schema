# MDR Schema

[![DOI:10.48505/nims.3239](https://img.shields.io/badge/DOI-10.48505%2Fnims.3239-blue)](https://doi.org/10.48505/nims.3239) [![License:CC-BY-4.0](https://img.shields.io/github/license/nims-dpfc/mdr-schema)](https://creativecommons.org/licenses/by/4.0/legalcode)

MDR Schemaは、物質・材料研究機構(NIMS)が運営する材料データリポジトリ「[Materials Data Repository (MDR)](https://mdr.nims.go.jp)」が採用するメタデータスキーマです。MDRは、[材料データプラットフォームDICE](https://dice.nims.go.jp)が提供するサービスの一つで、公的研究資金による研究成果を公開することで、新たな研究に繋げることを目的とするリポジトリサービスです。研究論文や、論文に付随する研究データ、および研究に資するプログラムなど、公知となった成果にDOIを付与して公開しており、データの引用やダウンロードが可能です。
MDRの詳細については、[DICEのWebサイト](https://dice.nims.go.jp/services/MDR/)をご覧ください。

MDR Schemaは、MDRでのデータ登録や検索の利便性の観点から、論文や研究データを登録する際に必要とする最低限のメタデータ項目を定義しています。本スキーマは、材料科学の幅広い分野からフィードバックを得ることを目的としてGitHubに公開するものであり、今後GitHubでのIssueやPull Requestを通して、スキーマの拡張や修正の提案を受け付ける予定です。


## 本リポジトリの内容

* schema.yaml: スキーマ定義ファイル
* metadata-sample.yaml: 全項目を記述したファイル
* metadata-sample-xafs.yaml: XAFSのデータを記述したサンプルファイル
* metadata-sample-minimum.yaml: 登録時の最小限の書誌メタデータと材料メタデータを記述したサンプルファイル

## 特長

MDR Schemaは、以下の点を特長としています。

### 簡潔なデータ構造

MDR Schemaは、MDRへのデータ登録を容易に行えるようにすることを目的として開発しています。MDR Schemaのデータ構造は、深い階層構造を持たない簡潔なものとなっており、研究者によるメタデータの記述を容易にするとともに、MDRでの高速かつ安定的なデータ登録処理を実現します。

### 識別子(ID)を用いたデータ間の連携

MDR Schemaは、識別子(ID)によるデータ記述と、それを用いたデータ間の連携を重視して設計しています。[DOI](https://doi.org/)や[ORCID](https://orcid.org/)など、研究発表に広く用いられているグローバルな識別子を用いて、各種の材料研究データ、それにそれをもとにした論文などの成果物とのリンクを行い、材料データの検索や入手をより容易にします。今後、機構内外の材料データベースのさまざまなID体系とも連携する予定です。

### 読み書きの容易さ

MDR Schemaは、YAMLで記述することを想定しています。
YAMLはJSONやCSVと異なり、メタデータファイルの中に自由にコメント（説明文）を追加することができます。材料メタデータの記述例をあらかじめ記述しておいたり、補足の情報を追加したりすることで、材料メタデータになじみのない方でも容易にメタデータの記述を行うことができます。

### さまざまなデータ作成方法をサポート

MDR Schemaで使用するYAMLはテキストフォーマットであり、どのようなソフトウェアでも作成できます。[Visual Studio Code](https://code.visualstudio.com/)など、YAMLをサポートしているテキストエディタであれば、項目名の色分け表示や自動入力によって、より快適にメタデータの作成を行うことができます。  
また、Python・Ruby・C言語などのプログラム言語でYAMLの入出力を行うライブラリを使用することで、実験データの生成と同時に、メタデータの作成を自動的に行うこともできます。

### メタデータの構文チェックが可能

MDR Schemaは、PythonのYAML検証ツールである[Yamale](https://github.com/23andMe/Yamale)を用いて、メタデータの構文を容易にチェックすることができます。これによって、誤った書式のメタデータをリポジトリに登録しようとしてエラーになる二度手間を防ぐことができます。

YamaleでのYAMLの構文チェックは、以下のようにして実行します。

```sh
$ pip install yamale
$ cd mdr-schema
$ yamale metadata-sample.yaml
```

### 既存のMDRでの材料メタデータ項目との互換性

MDR Schemaは、[現在のMDRで使用されているメタデータスキーマ](https://doi.org/10.48505/nims.3241)との互換性を持っています。MDR Schemaでメタデータを記述すれば、現在のMDRにも、機能追加が行われる将来のMDRにも材料データを登録することができます。

### 非独占的な利用ライセンス

MDR Schemaは、[クリエイティブ・コモンズ・ライセンス（表示） (CC-BY)](https://creativecommons.org/licenses/by/4.0/deed.ja)で公開しており、どなたでも自由に利用することができます。

## MDR Schemaの開発について

MDR Schemaは、物質・材料研究機構 統合型材料開発・情報基盤部門 材料データプラットフォームセンター (DPFC)が開発しています。スキーマへのご意見やご質問は、 schema@ml.nims.go.jp までお送りください。
