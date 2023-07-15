# glossary_semiconductor_design_terms_for_beginners
# 半導体初学者むけ単語集
※ ぼちぼち更新しています。追加して欲しい単語あれば連絡ください。

## 【おすすめ動画】

### [【京都賞記念講演】カーヴァー・ミード「情報革命の時代を生きて」](https://www.youtube.com/watch?v=_yjZi83SBZI)
[**Carver Andress Mead**](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%BC%E3%83%90%E3%83%BC%E3%83%BB%E3%83%9F%E3%83%BC%E3%83%89)教授の講演。EDA（集積回路設計ソフト）の生みの親です。チップ設計の歴史を俯瞰して理解することができます。

## 【A - F】

### [CTS](https://signoffsemiconductors.com/clock-tree-synthesis-1)
**Clock Tree Synthesis** の略。同期設計においてはフリップフロップへ供給される同期クロックの位相が完全に一致していることが望ましいが、同期クロック信号は、一番負荷が重く、配線長も長いことから、チップ内に分散されたフリップフロップに供給している同期クロック信号の位相を合わせる為には、特別な手当をする必要がある。具体的には、クロックバッファーの挿入やクロック配線の引き回し等により、消費電力とタイミング（最大動作周波数）の最適化を図る設計工程を指す。動作処理性能が最優先されるCPUやメモリ設計では、ツールに任せずに、人手でクロック配線とバッファーの配置を設計することもある。

### [DRC](https://en.wikipedia.org/wiki/Design_rule_checking)
**Design Rule Checking** の略。半導体プロセスの加工工程における物理的な寸法や公差から決められた設計制約の検証作業。PCBのパターン設計でのDRCと基本は同じ。最先端プロセスになるほどに設計制約は増加するので、DRCに必要なルールファイルは複雑化し実行時間も増加している。80年代、1umルールの頃は手書したレイアウト図面をミニコンでDRCを実行し、数十センチにもなるラインプリンター紙に出力されたエラーを一つ一つ人手で修正していた時代もあった。

### [Decap Cell](https://ivlsi.com/decap-cells-vlsi-physical-design/)
**Decap Cell** とは、電源間容量用のスタンダードセルの呼称。電源配線の寄生抵抗に由来する電源電圧のダイナミックな電圧降下を補償する為に、半導体回路を構成するスタンダードセルの近傍に電源間容量（通常はMOS容量素子）を配置する。

### [Filler Cell](https://vlsi.pro/physical-only-cells-filler-cells/)
**Filler Cell** とは、回路的には意味のないスタンダードセル(Filler Cell）をレイアウト上の空き地を埋めることで、DRCエラー等の物理的な不都合を解消する為のセル。

## 【G - L】
### [GDSII](https://en.wikipedia.org/wiki/GDSII) 
半導体Layout用のファイルフォーマット(**Graphic Design System II**の略).1970年末に商用化されたLayout設計装置([Calma](https://en.wikipedia.org/wiki/Calma))が採用したファイルフォーマット。最近だと[GDSFACTORY](https://gdsfactory.github.io/gdsfactory/index.html)等のオープンソースなツールもある。

### [LPE](https://en.wikipedia.org/wiki/Parasitic_extraction)
**Layout Parasitic Extraction** の略。レイアウト情報から回路図には明示的に記述されていない寄生素子（RLC）を抽出して[SPICE](https://en.wikipedia.org/wiki/SPICE)等のネット情報として出力するツール。膨大な数の寄生素子が出力されることで回路シミュレーションが実行できないという課題に対応するために、寄生素子を電気的に等価な記述に圧縮記述する機能がある。ロジック設計ではネットの遅延情報としてフィードバックされる。

### [LVS](https://en.wikipedia.org/wiki/Layout_Versus_Schematic)
**Layout Versus Schematic** の略。回路図とレイアウトの比較検証作業。回路図から抽出したネット情報とレイアウトから抽出したネット情報の等価性チェック。[SPICE](https://en.wikipedia.org/wiki/SPICE)や[CDL](https://en.wikipedia.org/wiki/Circuit_design_language)記述のネットを使って等価検証を行う。手書きの回路図しか無かった80年代では、人手でレイアウトの逆読みと手書き回路図との比較をダブル・トリプルに検証していた時代もあった。

## 【M - R】
### [PDK](https://en.wikipedia.org/wiki/Process_design_kit#)
**Process Design Kit** の略。半導体プロセスに依存した設計に必要な設定情報一般の呼称。設計ツール毎に必要な、Technology file 群（Spice model や DRC/LVS の runset、Layer ファイル等）と、回路設計に必要な、回路Symbolや、基本Library(IO や Standard Cell, Pcell, SRAM 等）に大きく分けられます。実態を理解せずに概念的にPDKという単語を使う人もいるので注意。

## 【S - W】

### [SKILL](https://en.wikipedia.org/wiki/Cadence_SKILL)
[**CADENCE**](https://www.cadence.com/en_US/home.html)が提供する（Cadenceに統合される前のSDA社時代からSKILLは存在する）EDA設計ツールにバンドルされたスクリプト言語。基本は[LISP](https://ja.wikipedia.org/wiki/LISP)だが、設計データーベースのオブジェクトへアクセスができるのが特徴（だと理解している）。個人的にはテキストエディタのEmacsとスクリプト言語であるEmacs-Lispの関係と同じだと理解。SKILL言語に精通してCADENCEツールをカスタマイズできるエンジニアを「Skiller(スキラー)」と称するという噂がある。

### [Standard Cell](https://en.wikipedia.org/wiki/Standard_cell)
**SC**とか**スタセル**とか短縮されて呼ばれることが多い。デジタル回路設計用のRTL記述言語([Verilog](https://en.wikipedia.org/wiki/Verilog)や[VHDL](https://en.wikipedia.org/wiki/VHDL))から論理合成ツールを介して最終的にネットとして展開される基本回路（Inverter/NAND/NOR/FF等）群のレイアウトとタイミング(遅延等）情報をまとめたファイル(.lib）を指す。同じ基本回路（例えばInverter)でもネット負荷に応じた駆動能力を持つ複数の素子がライブラリに登録されている。一般にタイミング（遅延）と消費電力はトレードオフの関係にあるので、クリティカルパスを解決するために特別なスタセルを特注・置き換えてタイミングエラーを回避するすることも行われる。また、OAI/AOI等の複合ゲートや、スキャン挿入用のDFF等の特殊回路を登録することも一般的である。

### [TAP]


## 【X - Z】

