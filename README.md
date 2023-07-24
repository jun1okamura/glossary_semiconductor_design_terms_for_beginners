# glossary_semiconductor_design_terms_for_beginners
# 半導体初学者むけ半導体設計の用語集
※ ぼちぼち更新しています。追加して欲しい単語あれば連絡ください。

## 【おすすめ動画】

### [【京都賞記念講演】カーヴァー・ミード「情報革命の時代を生きて」](https://www.youtube.com/watch?v=_yjZi83SBZI)
[**Carver Andress Mead**](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%BC%E3%83%90%E3%83%BC%E3%83%BB%E3%83%9F%E3%83%BC%E3%83%89)教授の講演。EDA（集積回路設計ソフト）の生みの親です。チップ設計の歴史を俯瞰して理解することができます。

## 【A - F】

### [AFE]()

### [AXI]()

### [BIST]()

### [Compiler](https://ja.wikipedia.org/wiki/Design_Compiler)
半導体設計におけるコンパイラーとは**論理合成ツール**のことを指す。抽象度の高い回路記述であるRTL記述から、**Standard Cell**ライブラリーに登録してあるゲート素子の組み合わせ記述（ネットリスト）に変換する処理及びツール。ソフトウェアの高位言語記述(C言語)を命令セット(ISA)に変換する処理であるコンパイラーに呼応している。商用のツールでは、[**Design Compiler(Synopsys)**](https://www.synopsys.com/implementation-and-signoff/rtl-synthesis-test/design-compiler-graphical.html)や[**Encounter/Genus(Cadence)**](https://www.cadence.com/en_US/home/tools/digital-design-and-signoff/synthesis.html)がある。オープン系ではの[**Yosys**](https://yosyshq.net/)が有名→[GitHub](https://github.com/YosysHQ/yosys)

### [CTS](https://ivlsi.com/clock-tree-synthesis-cts-vlsi-physical-design/)
**Clock Tree Synthesis** の略。同期設計においてはフリップフロップへ供給される同期クロックの位相が完全に一致していることが望ましいが、同期クロック信号は、一番負荷が重く、配線長も長いことから、チップ内に分散されたフリップフロップに供給している同期クロック信号の位相を合わせる為には、特別な手当をする必要がある。具体的には、クロックバッファーの挿入やクロック配線の引き回し等により、消費電力とタイミング（最大動作周波数）の最適化を図る設計工程を指す。動作処理性能が最優先されるCPUやメモリ設計では、ツールに任せずに、人手でクロック配線とバッファーの配置を設計することもある。

### [DFM]()

### [DFT]()

### [DLL]()

### [DRC](https://en.wikipedia.org/wiki/Design_rule_checking)
**Design Rule Checking** の略。半導体プロセスの加工工程における物理的な寸法や公差から決められた設計制約の検証作業。PCBのパターン設計でのDRCと基本は同じ。最先端プロセスになるほどに設計制約は増加するので、DRCに必要なルールファイルは複雑化し実行時間も増加している。80年代、1umルールの頃は手書したレイアウト図面をミニコンでDRCを実行し、数十センチにもなるラインプリンター紙に出力されたエラーを一つ一つ人手で修正していた時代もあった。

### [Decap Cell](https://ivlsi.com/decap-cells-vlsi-physical-design/)
**Decap Cell** とは、電源間容量用のスタンダードセルの呼称。電源配線の寄生抵抗に由来する電源電圧のダイナミックな電圧降下を補償する為に、半導体回路を構成するスタンダードセルの近傍に電源間容量（通常はMOS容量素子）を配置する。

### [ECO]()

### [FILL](https://semiengineering.com/knowledge_centers/materials/fill)
**Metal Fill**や**Poly Fill**とも言われる。[**CMP**](https://en.wikipedia.org/wiki/Chemical-mechanical_polishing)による平坦化プロセス工程において、デッシング現象（広いメタル間スペースが過度のエッチングで皿状に凹んでしまう事）を防ぐ為に、電気的には意味のないメタルやポリ層を配置する作業。通常はレイアウト設計が完全に終わった最終工程で実行される。

### [Filler Cell](https://vlsi.pro/physical-only-cells-filler-cells/)
**Filler Cell** とは、スタンダードセル間の隙間に挿入してレイアウト上の空き地を埋めることで、電源接続とDRCエラー等の物理的な不都合を解消する為のセル。

### [Formal Verifier](https://en.wikipedia.org/wiki/Formal_verification)
半導体設計における **Formal Verifier** (形式的検証)とは、回路記述間を数学的に解析することで，記述間(例えばRTL記述とゲート記述)の正当性を検証する手法である。シミュレータのように回路を動作させて検証するのではないので、シミュレーション・パターンの作成が不要で，かつ高速・網羅的に検証できるというメリットがある。

## 【G - L】

### [GDSII](https://en.wikipedia.org/wiki/GDSII) 
半導体Layout用のファイルフォーマット(**Graphic Design System II**の略).1970年末に商用化されたLayout設計装置([Calma](https://en.wikipedia.org/wiki/Calma))が採用したファイルフォーマット。最近だと[GDSFACTORY](https://gdsfactory.github.io/gdsfactory/index.html)等のオープンソースなツールもある。

### [GPIO]()

### [HLS](https://en.wikipedia.org/wiki/High-level_synthesis)
**High-level synthesis** の略。RTL記述よりさらに抽象度を上げた記述からロジック回路を設計する手法。　C++と同様の言語仕様をベースに拡張した[**System-C**](https://en.wikipedia.org/wiki/SystemC)や、Verilogを拡張した[**SystemVerilog**](https://en.wikipedia.org/wiki/SystemVerilog)、Googleが開発しているOSSの[**XLS**](https://github.com/google/xls)等、その他にもいろいろある。

### [I2C]()

### [I2S]()

### [IBIS]()

### [JTAG]()

### [KGD]()

### [LDO]()

### [LIB](https://en.wikipedia.org/wiki/Standard_cell)
**Liberty Timing Format** 記述のファイル(.lib)を指す。**Standard Cell**ライブラリの遅延/消費電力などの特性を記述したファイル。微細化に伴い、ばらつきに対応した拡張フォーマットには CCS(Composite Current Source)やECSM(effective current source model)などがある。遅延情報はSDF(Standard Delay Format: IEEE std 1497-2001)を用いてネットリストの各ネットにバックアノテートされる。

### [LPE](https://en.wikipedia.org/wiki/Parasitic_extraction)
**Layout Parasitic Extraction** の略。レイアウト情報から回路図には明示的に記述されていない寄生素子（RLC）を抽出して[SPICE](https://en.wikipedia.org/wiki/SPICE)等のネット情報として出力するツール。膨大な数の寄生素子が出力されることで回路シミュレーションが実行できないという課題に対応するために、寄生素子を電気的に等価な記述に圧縮記述する機能がある。ロジック設計ではネットの遅延情報としてフィードバックされる。

### [LVS](https://en.wikipedia.org/wiki/Layout_Versus_Schematic)
**Layout Versus Schematic** の略。回路図とレイアウトの比較検証作業。回路図から抽出したネット情報とレイアウトから抽出したネット情報の等価性チェック。[SPICE](https://en.wikipedia.org/wiki/SPICE)や[CDL](https://en.wikipedia.org/wiki/Circuit_design_language)記述のネットを使って等価検証を行う。手書きの回路図しか無かった80年代では、人手でレイアウトの逆読みと手書き回路図との比較をダブル・トリプルに検証していた時代もあった。

## 【M - R】

### [NOC]()

### [OPC]()

### [OTP]()

### [PDK](https://en.wikipedia.org/wiki/Process_design_kit#)
**Process Design Kit** の略。半導体プロセスに依存した設計に必要な設定情報一般の呼称。設計ツール毎に必要な、Technology file 群（Spice model や DRC/LVS の runset、Layer ファイル等）と、回路設計に必要な、回路Symbolや、基本Library(IO や Standard Cell, Pcell, SRAM 等）に大きく分けられます。実態を理解せずに概念的にPDKという単語を使う人もいるので注意。

### [PLL]()

### [QFN]()

### [QFP]()

### [RAM generator](https://soclabs.org/design-flow/memory-generators)
LSIに内蔵されるメモリは[**SRAM**](https://en.wikipedia.org/wiki/Static_random-access_memory)が一般的で、商用では各種の[**Memory Compiler**](https://www.synopsys.com/dw/ipdir.php?ds=dwc_sram_memory_compilers)が用意されている。メモリコンパイラは、動作周波数、ポート数、アドレス幅、データ幅等をパラメータとして入力すると最適なメモリのライブラリ情報を自動生成するツールである。商用メモリコンパイラでは、メモリセル(BitCell)に特別なデザインルールを採用することで必要なシリコン面積を圧縮するものもある。オープン系では[**OpenRAM**](https://openram.org/)が有名で、2ポート(同時に読み書き可能）メモリにも対応している。

### [RDL]()

### [RTL](https://en.wikipedia.org/wiki/Register-transfer_level)
**Register-transfer level** の略、ロジック回路の抽象的な記述レベル。ラッチ回路などの順序回路に相当する最小の部分を「レジスタ」として抽象化して、ロジック回路の動作を、レジスタからレジスタへの転送とその間の組合せ論理回路によるロジック演算の組み合わせとして記述する。言語仕様として[**Verilog**](https://en.wikipedia.org/wiki/Verilog)や[**VHDL**](https://en.wikipedia.org/wiki/VHDL)が標準化されている。C等の高級ソフトウェア言語と比べると、ロジックゲートや配線等のハードウェアを意識して記述する必要があり、初学者には難しいと感じることも多い。

## 【S - W】

### [SCAN]()

### [SDC](https://www.macnica.co.jp/business/semiconductor/articles/intel/133417)
**Synopsys Design Constraint**の略。Synopsys社によって開発された設計制約のフォーマット、現在では業界標準になっている。回路が満たすべきタイミング情報（クロックの周期等）を記載する。

### [SERDES]()

### [SDF](https://en.wikipedia.org/wiki/Standard_Delay_Format)
**Standard Delay Format**の略。遅延情報を記述する[IEEE標準フォーマット](https://ieeexplore.ieee.org/document/972829)。パスの遅延時間や遅延時間の制約条件、配線遅延時間なども扱うことができる。

### [SKILL](https://en.wikipedia.org/wiki/Cadence_SKILL)
[**CADENCE**](https://www.cadence.com/en_US/home.html)が提供する（Cadenceに統合される前のSDA社時代からSKILLは存在する）EDA設計ツールにバンドルされたスクリプト言語。基本は[LISP](https://ja.wikipedia.org/wiki/LISP)だが、設計データーベースのオブジェクトへアクセスができるのが特徴（だと理解している）。個人的にはテキストエディタのEmacsとスクリプト言語であるEmacs-Lispの関係と同じだと理解。SKILL言語に精通してCADENCEツールをカスタマイズできるエンジニアを「Skiller(スキラー)」と称するという噂がある。

### [SPI]()

### [SPICE](https://en.wikipedia.org/wiki/SPICE)
**Simulation Program with Integrated Circuit Emphasis** の略。キルヒホッフの回路方程式を解く回路シミュレーター。1970年代にUC BerkeleyでFORTRAN言語で開発され、SPICE2G6版で実用的に使われるようになった（商用や国内大手が自社開発していたSPICEは、SPICE2G6をルーツにしていた）。商用のSPICEでは、[**HSPICE(Synopsys)**](https://www.synopsys.com/ja-jp/implementation-and-signoff/ams-simulation/primesim-hspice.html)や[**Spector(Cadence)**](https://www.cadence.com/ja_JP/home/tools/custom-ic-analog-rf-design/circuit-simulation.html)がデファクト。オープン系ではC言語に書き直されたSPICE3版がベースの[**Ngspice**](https://ngspice.sourceforge.io/)や、並列化に優れた行列ソルバーを導入した[**Xyce**](https://xyce.sandia.gov/)が有名。フリーのSPICEでは[**LTspice(Analog Device)**](https://www.analog.com/jp/design-center/design-tools-and-calculators/ltspice-simulator.html)が有名。

### [Standard Cell](https://en.wikipedia.org/wiki/Standard_cell)
**SC**とか**スタセル**とか短縮されて呼ばれることが多い。デジタル回路設計用のRTL記述言語([Verilog](https://en.wikipedia.org/wiki/Verilog)や[VHDL](https://en.wikipedia.org/wiki/VHDL))から論理合成ツールを介して最終的にネットとして展開される基本回路（Inverter/NAND/NOR/FF等）群のレイアウトとタイミング(遅延等）情報をまとめたファイル(.lib）を指す。同じ基本回路（例えばInverter)でもネット負荷に応じた駆動能力を持つ複数の素子がライブラリに登録されている。一般にタイミング（遅延）と消費電力はトレードオフの関係にあるので、クリティカルパスを解決するために特別なスタセルを特注・置き換えてタイミングエラーを回避するすることも行われる。また、OAI/AOI等の複合ゲートや、スキャン挿入用のDFF等の特殊回路を登録することも一般的である。

### [STA](https://en.wikipedia.org/wiki/Static_timing_analysis)
**Static Timing Analysis**の略。タイミング検証方法の一つ。入力から出力（同期回路の場合はFFからFF）までの経路に関して遅延の合計を計算し、**SDC**ファイルに記載された設計タイミング条件を満たされているかどうかを検証する。各経路の最大遅延を合計してセットアップ条件を満たしているか、各部の最小遅延を合計してホールド条件を満たしているか、両者のチェックを行う。[**Prime Time(Synopsys)**](https://www.synopsys.com/implementation-and-signoff/signoff/primetime.html)がデファクト。オープン系には[**OpenSTA**](https://github.com/The-OpenROAD-Project/OpenSTA)がある。

### [Tap Cell](https://ivlsi.com/tap-cell-placement-vlsi-physical-design/)
チップの基板層（Nwell/Pwell)への電源供給用のセル。適当な間隔で基板へ電源を接続して基板層のインピーダンスを下げて[**ラッチアップ**](https://en.wikipedia.org/wiki/Latch-up)によるチップの破壊を予防する。半導体物理をかじっていないと全く意味不明だが、ひたすらDRCのエラーを消さないと大変なことになる。

## 【X - Z】

### [Verilog]()

### [VHDL]()

### [WCSP]()

### [WIP]()
