# glossary_semiconductor_design_terms_for_beginners
# 半導体初学者むけ単語集
※ ぼちぼち更新しています。追加して欲しい単語あれば連絡ください。

## 【A - F】
### [DRC](https://en.wikipedia.org/wiki/Design_rule_checking)

**Design Rule Checking** の略。半導体プロセスの加工工程における物理的な寸法や公差から決められた設計制約の検証作業。PCBのパターン設計でのDRCと基本は同じ。最先端プロセスになるほどに設計制約は増加するので、DRCに必要なルールファイルは複雑化し実行時間も増加している。80年代、1umルールの頃は手書したレイアウト図面をミニコンでDRCを実行し、数十センチにもなるラインプリンター紙に出力されたエラーを一つ一つ人手で修正していた時代もあった。

### [LVS](https://en.wikipedia.org/wiki/Layout_Versus_Schematic)

**Layout Versus Schematic** の略。回路図とレイアウトの比較検証作業。回路図から抽出したネット情報とレイアウトから抽出したネット情報の等価性チェック。[SPICE](https://en.wikipedia.org/wiki/SPICE)や[CDL](https://en.wikipedia.org/wiki/Circuit_design_language)記述のネットを使って等価検証を行う。手書きの回路図しか無かった80年代では、人手でレイアウトの逆読みと手書き回路図との比較をダブル・トリプルに検証していた時代もあった。

## 【G - L】
### [GDSII](https://en.wikipedia.org/wiki/GDSII) 
半導体Layout用のファイルフォーマット(**Graphic Design System II**の略).1970年末に商用化されたLayout設計装置([Calma](https://en.wikipedia.org/wiki/Calma))が採用したファイルフォーマット。最近だと[GDSFACTORY](https://gdsfactory.github.io/gdsfactory/index.html)等のオープンソースなツールもある。

## 【M - R】
### [PDK](https://en.wikipedia.org/wiki/Process_design_kit#)
**Process Design Kit** の略。半導体プロセスに依存した設計に必要な設定情報一般の呼称。設計ツール毎に必要な、Technology file 群（Spice model や DRC/LVS の runset、Layer ファイル等）と、回路設計に必要な、回路Symbolや、基本Library(IO や Standard Cell, Pcell, SRAM 等）に大きく分けられます。実態を理解せずに概念的にPDKという単語を使う人もいるので注意。

### [SKILL](https://en.wikipedia.org/wiki/Cadence_SKILL)
[**CADENCE**](https://www.cadence.com/en_US/home.html)が提供する（Cadenceに統合される前のSDA社時代からSKILLは存在する）EDA設計ツールにバンドルされたスクリプト言語。基本は[LISP](https://ja.wikipedia.org/wiki/LISP)だが、設計データーベースのオブジェクトへのアクセスができるのが特徴（だと理解している）。個人的にはテキストエディタのEmacsとスクリプト言語であるEmacs-Lispの関係と同じだ理解。日本だとSKILL言語に精通してCADENCEツールをカスタマイズできるエンジニアを「Skiller(スキラー)」と称するという噂がある。

## 【S - W】

## 【X - Z】

