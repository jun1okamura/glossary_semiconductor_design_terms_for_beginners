# glossary_semiconductor_design_terms_for_beginners
# 半導体初学者むけ「半導体設計で使われる用語集」
※ ぼちぼち更新しています。追加して欲しい用語・略語等あれば連絡ください。

## 【おすすめ動画】

### [【京都賞記念講演】カーヴァー・ミード「情報革命の時代を生きて」](https://www.youtube.com/watch?v=_yjZi83SBZI)
[**Carver Andress Mead**](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%BC%E3%83%90%E3%83%BC%E3%83%BB%E3%83%9F%E3%83%BC%E3%83%89)教授の講演。EDA（集積回路設計ソフト）の生みの親です。チップ設計の歴史を俯瞰して理解することができます。

## 【A - F】

### [AFE](https://en.wikipedia.org/wiki/Analog_front-end)　(**IPブロック(Hard IP)**)
**Analog Front-End** の略。センサー等のアナログ出力信号をデジタル信号へ変換するアナログ回路を指す。一般には、アンプやA/Dコンバータ、フィルタなどのアナログ回路を指すことが多いが、高速シリアル通信向けのクロックが重畳された小振幅信号やPAM(Pulse Amplitude Modulation)信号に変調された信号をデジタル信号に復調するミックスドシグナル回路もAFEと呼ぶことがある。SoC内部にAFEを搭載する場合と、SoCとは別チップでAFEを構成する場合がある。

### [AXI](https://en.wikipedia.org/wiki/Advanced_eXtensible_Interface)　(**Design Standard**)
**Advanced eXtensible Interface**の略。AMBA(Advanced Microcontroller Bus Architecture)規格の一部として ARM により[定義された](https://developer.arm.com/documentation/ihi0022/latest/)チップ内部のIP間のバスインターフェース規格。IP間で valid/ready のハンドシェイク動作をして有効データを判断する。

### [BGR]() (**IPブロック(Hard IP)**)

### [BIST](https://en.wikipedia.org/wiki/Built-in_self-test)　(**Design Knowledge**)
**Buit-in Self TEST**の略。設計した回路の動作チェックを内蔵したテスト用の回路を使ってテストすること。費用のかかる半導体専用テスターを使わずに合否を判定する。内蔵メモリのテストに使われることが多いが、メモリ以外にもAFE回路等の半導体専用テスターではテスト出来ない回路のテストの為に利用される。

### [CDR](https://en.wikipedia.org/wiki/Clock_recovery)　(**IPブロック(Hard IP)**)
**Clock and Data Recovery** の略。データとクロックを重畳させたシリアル信号から、受信側でクロック成分とデータ成分を切り分ける回路を指す。送信側では、データに含まれるエッジの場所や数を保証して変調し、受信側で信号に含まれるクロック成分をPLL同期させることでクロックを抽出し、抽出したクロックでデータを復調する。

### [CS]()　(**Design Knowledge**)

### [CSR]()　(**Design Knowledge**)

### [CTS](https://ivlsi.com/clock-tree-synthesis-cts-vlsi-physical-design/)　(**EDA Methodology/tool**)
**Clock Tree Synthesis** の略。同期設計においてはフリップフロップへ供給される同期クロックの位相が完全に一致していることが望ましいが、同期クロック信号は、一番負荷が重く、配線長も長いことから、チップ内に分散されたフリップフロップに供給している同期クロック信号の位相を合わせる為には、特別な手当をする必要がある。具体的には、クロックバッファーの挿入やクロック配線の引き回し等により、消費電力とタイミング（最大動作周波数）の最適化を図る設計工程を指す。動作処理性能が最優先されるCPUやメモリ設計では、ツールに任せずに、人手でクロック配線とバッファーの配置を設計することもある。

### [DDR]()　(**Design Standard**)

### [DFM](https://en.wikipedia.org/wiki/Design_for_manufacturability)　(**EDA Methodology/Tool**)
**Design For Manufacturability**の略。半導体設計におけるDFMは、製造されたチップの歩留まり率(Yield)を上げる為に行われる設計段階での工夫のことを総称する。DFMツールは、ポリ・メタル挿入(CMPでのDishing対策）、ダブルVIA挿入(VIAのオープン対策)、配線拡張（配線切れ対策）などを行うツールである。リソグラフィーの解像度を改善する(OPC=Optical Proximity Correction：光学近接効果補正)為の補助パターン挿入ツールも広義のDFMツールに含まれる。またメモリの冗長回路・ECC回路の採用、カスタムレイアウト設計で「最小寸法をなるべく避ける」等も広義のDFMに含まれる。

### [DFT](https://en.wikipedia.org/wiki/Design_for_testing)　(**EDA Methodology/Tool**)
**Design For Testing** or **Design For Testability**の略。日本語だと「テスト容易化設計」であるが、言い換えると「LSIのテストの実行を容易にするための回路設計手法」の総称を指す。具体的には、テストモードとしての独自機能を備えたLSI、セルフテスト回路を設けたLSI、論理回路のテストのためのスキャンパスを設けたLSI、CMOSの暗電流に着目したテスト手法、等々がある。採用する手法、技術と必要なシリコン面積等のオーバーヘッドと、テスト容易化で得られるテストコスト削減効果のバランスが重要である。

### [DLL](https://en.wikipedia.org/wiki/Delay-locked_loop)　(**IPブロック(Hard IP)**)
**Delay Locked Loop**の略。外部クロックとインバーター（遅延をアナログ的に制御する場合と、量子化された遅延をデジタル的に選択する場合がある）の遅延信号との間で位相をロックをすることで、負の遅延を持ったクロック信号を発生して、セットアップ・ホールドのタイミングマージンを改善できる。同様に外部クロックに対して複数の位相を持った多層クロックを発生したり、数多くの応用回路が提案されている。PLLと比較して、外部クロックの位相の変化に瞬時に追随できる利点がある一方で、PLLの様に、任意の逓倍クロックを発生することは出来ない。

### [DRC](https://en.wikipedia.org/wiki/Design_rule_checking)　(**EDA Methodology/Tool**)
**Design Rule Checking** の略。半導体プロセスの加工工程における物理的な寸法や公差から決められた設計制約の検証作業。PCBのパターン設計でのDRCと基本は同じ。最先端プロセスになるほどに設計制約は増加するので、DRCに必要なルールファイルは複雑化し実行時間も増加している。80年代、1umルールの頃は手書したレイアウト図面をミニコンでDRCを実行し、数十センチにもなるラインプリンター紙に出力されたエラーを一つ一つ人手で修正していた時代もあった。

### [Decap Cell](https://ivlsi.com/decap-cells-vlsi-physical-design/)　(**Design Knowledge**)
**Decap Cell** とは、電源間容量用のスタンダードセルの呼称。電源配線の寄生抵抗に由来する電源電圧のダイナミックな電圧降下を補償する為に、半導体回路を構成するスタンダードセルの近傍に電源間容量（通常はMOS容量素子）を配置する。

### [ECO](https://en.wikipedia.org/wiki/Engineering_change_order)　(**EDA Methodology/Tool**)
**Engineering Change Order**の略。P&R等の物理設計が完了したデザインの最終段階での回路変更を、一般にECOと呼ぶ。**pre-mask ECO**(Standard Cellの置き換えあり）と**post-mask ECO**(未使用のStandard Cell(ECO用セル）だけをつかう）に区別して使う場合もある。設計フローの上流に戻らずに、デザイン機能の変更やバグ修正を配線と未使用のStandard Cell(置き換えやECO用セル）を利用して実現する手続きのこと。ECOをサポートするツールもある。

### [ES]()　(**Design Knowledge**)

### [FILL](https://semiengineering.com/knowledge_centers/materials/fill)　(**EDA Methodology/Tool**)
**Metal Fill**や**Poly Fill**とも言われる。[**CMP**](https://en.wikipedia.org/wiki/Chemical-mechanical_polishing)による平坦化プロセス工程において、デッシング現象（広いメタル間スペースが過度のエッチングで皿状に凹んでしまう事）を防ぐ為に、電気的には意味のないメタルやポリ層を配置する作業。通常はレイアウト設計が完全に終わった最終工程で実行される。DFMの一種。

### [Filler Cell](https://vlsi.pro/physical-only-cells-filler-cells/)　(**Design Knowledge**)
**Filler Cell** とは、スタンダードセル間の隙間に挿入してレイアウト上の空き地を埋めることで、電源接続とDRCエラー等の物理的な不都合を解消する為のセル。

### [Formal Verification](https://en.wikipedia.org/wiki/Formal_verification)　(**EDA Methodology/Tool**)
半導体設計における **Formal Verification** (形式的検証)とは、回路記述間を数学的に解析することで，記述間(例えばRTL記述とゲート記述)の論理が等価であるかどうかの検証（等価性検証）や、回路記述が動作性能に関する記述を満たしているかの検証（プロパティ検証）がある。シミュレータのように回路を動作させて検証するのではないので、シミュレーション・パターンの作成が不要で，かつ高速・網羅的に検証できるというメリットがある。

## 【G - L】

### [GDSII](https://en.wikipedia.org/wiki/GDSII)  (**Design Standard**)
半導体Layout用のファイルフォーマット(**Graphic Design System II**の略).1970年末に商用化されたLayout設計装置([Calma](https://en.wikipedia.org/wiki/Calma))が採用したファイルフォーマット。最近だと[GDSFACTORY](https://gdsfactory.github.io/gdsfactory/index.html)等のオープンソースなツールもある。

### [GPIO](https://en.wikipedia.org/wiki/General-purpose_input/output)　(**IPブロック(IO-PAD)**)
**General Purpose Input/Output**の略。文字通り汎用IO回路、入出力設定、ドライブ電流調整、プルアップ・プルダウン、トライステート機能等が、ソフトウェアやレジスターにて設定できる。一般にはGPIOピンは、低速インターフェースやアナログ入出力と兼ねる場合が多い。

### [HLS](https://en.wikipedia.org/wiki/High-level_synthesis)　(**Design Knowledge**)
**High-level synthesis** の略。RTL記述よりさらに抽象度を上げた記述からロジック回路を設計する手法。システム設計、ハードウェア設計向けの C++ クラスライブラリである[**SystemC**](https://en.wikipedia.org/wiki/SystemC)や、Googleが開発しているオープン系の[**XLS**](https://github.com/google/xls)等、その他にもいろいろある。

### [I2C](https://en.wikipedia.org/wiki/I%C2%B2C)　(**IPブロック(Soft-IP)**)
**Inter-Integrated Circuit** の略。SDAとSCLのフィリップス社で開発された２線デジタルインターフェース。転送スピードは100K/400KHz、プルアップ抵抗でLo-Hiをドライブする仕様の為に高速動作や長距離伝送は難しい。通信に必要な信号線が少ないことと、回路規模が小さいことから、多くのセンサーやAD/DAコンバーター、ファン制御、小型LCDパネル、LEDアレー等で使われている。アイ・スクエア・シーもしくはアイ・ツー・シーと呼ぶ。

### [I2S](https://en.wikipedia.org/wiki/I%C2%B2S)　(**IPブロック(Soft-IP)**)
**Inter-IC Sound** の略。デジタルPCM信号(音声)向けのフィリップス社で開発されたデジタルインターフェース。BCLK/LRCLK/DATAの3線で接続する場合とMCLKを加えた4線で接続する場合がある。2チャンネルのステレオ対応のI2Sを多チャンネルに拡張したTDM(Time Division Multiplexing)フォーマットもある。IISとは略さないので注意。

### [IBIS](https://en.wikipedia.org/wiki/Input/output_Buffer_Information_Specification)　(**Design Standard**)
**Input/output Buffer Information Specification** の略。PCBボード上のLSIチップ間の接続をシミュレーターにて検証する際に利用されるIOの特性モデル。実際のIOの回路を電圧電流源やRLC回路でモデル化することで、複数ベンダーのチップ間のPCBボードを含む信号品質やタイミング検証が可能となる。

### [JTAG](https://en.wikipedia.org/wiki/JTAG)　(**Design Standard**)
**Joint Test Action Group** の略。業界標準のテスト手法、PCBの基板検査のための標準規格から始まった。インタフェースの仕様は[IEEE1149.1](https://www.ti.com/lit/an/ssya002c/ssya002c.pdf)で定められているが、実際には半導体メーカーがプライベート命令やオプションレジスタを使って拡張している為に「総合デバッグインタフェース」になっている。TCK/TDI/TDO/TMSの4線とTRSTの5線を使う場合がある。FPGAの書き込みや、CPUのデバッグ、基板検査、ICの内部回路のテスト等に使われる。

### [KGD](https://xtech.nikkei.com/dm/article/WORD/20090121/164414/)　(**Design Knowledge**)
**Known Good Die** の略。良品のベア・チップを指す通称。複数のチップを1つのパッケージに収めるMCP(Multi-Chip Package)やチップレット，縦に積んだ複数のチップ間を貫通電極で接続する3次元実装などでは，実装する前に良品チップであることが保証されていないと、実装後の不良品が多く発生する問題がある。チップを提供する側と実装する側は、相反するコスト分担関係にある為に、KGD自体の動作保証レベル・品質保証レベルに関しては個別の対応されている。

### [LDO](https://en.wikipedia.org/wiki/Low-dropout_regulator)　(**IPブロック(Hard IP)**)
**Low Dropout Regulator** の略。ディスクリート部品の三端子レギュレーターの事。チップ内部で使用する電源を、外部から入力された電源から降圧する回路。高電圧側(外部)と降圧電圧(内部)の間に可変抵抗（=トランジスター）を直列に挿入して降圧側の負荷電流に応じて降圧電圧が一定になる様に制御することから、シリーズ・レギュレーターとも言われる。

### [LIB](https://en.wikipedia.org/wiki/Standard_cell)　(**Design Standard**)
**Liberty Timing Format** 記述のファイル(.lib)を指す。**Standard Cell**ライブラリの遅延/消費電力などの特性を記述したファイル。微細化に伴い、ばらつきに対応した拡張フォーマットには CCS(Composite Current Source)やECSM(effective current source model)などがある。遅延情報はSDF(Standard Delay Format: IEEE std 1497-2001)を用いてネットリストの各ネットにバックアノテートされる。

### [LPE](https://en.wikipedia.org/wiki/Parasitic_extraction)　(**EDA Methodology/Tool**)
**Layout Parasitic Extraction** の略。レイアウト情報から回路図には明示的に記述されていない寄生素子（RLC）を抽出して[SPICE](https://en.wikipedia.org/wiki/SPICE)等のネット情報として出力するツール。膨大な数の寄生素子が出力されることで回路シミュレーションが実行できないという課題に対応するために、寄生素子を電気的に等価な記述に圧縮記述する機能がある。ロジック設計ではネットの遅延情報としてフィードバックされる。

### [LVDS]()  (**IPブロック(Hard IP)**)

### [LVS](https://en.wikipedia.org/wiki/Layout_Versus_Schematic)　(**EDA Methodology/Tool**)
**Layout Versus Schematic** の略。回路図とレイアウトの比較検証作業。回路図から抽出したネット情報とレイアウトから抽出したネット情報の等価性チェック。[SPICE](https://en.wikipedia.org/wiki/SPICE)や[CDL](https://en.wikipedia.org/wiki/Circuit_design_language)記述のネットを使って等価検証を行う。手書きの回路図しか無かった80年代では、人手でレイアウトの逆読みと手書き回路図との比較をダブル・トリプルに検証していた時代もあった。

## 【M - R】

### [Master/Slave](https://en.wikipedia.org/wiki/Master/slave_(technology))　(**Design Knowledge**)
デバイス間の接続関係の総称。ハードウェアだけでなくソフトウェアでの実装でも使われる。2020年頃より差別的な用語の見直しが広がり、ホスト/クライアントやMain/Secondary(M/Sが使えるから）との言い回しを使うようになっている。ホスト側デバイスがクライアント側デバイスに出した指示に応じて、クライアント側デバイスが応答する接続関係。

### [MP]()　(**Design Knowledge**)

### [NOC]() 

### [OPC]()　(**Design Knowledge**)

### [OTP]()　(**IPブロック(Hard IP)**)

### [PDK](https://en.wikipedia.org/wiki/Process_design_kit#)　(**Design Knowledge**)
**Process Design Kit** の略。半導体プロセスに依存した設計に必要な設定情報一般の呼称。設計ツール毎に必要な、Technology file 群（Spice model や DRC/LVS の runset、Layer ファイル等）と、回路設計に必要な、回路Symbolや、基本Library(IO や Standard Cell, Pcell, SRAM 等）に大きく分けられます。実態を理解せずに概念的にPDKという単語を使う人もいるので注意。

### [PDN]()　(**Design Knowledge**)

### [PLL]()　(**IPブロック(Hard IP)**)

### [QFN]()　(**Design Knowledge**)

### [QFP]()　(**Design Knowledge**)

### [QSPI]()　(**IPブロック(Soft-IP)**)

### [RAM generator](https://soclabs.org/design-flow/memory-generators)　(**Design Knowledge**)
LSIに内蔵されるメモリは[**SRAM**](https://en.wikipedia.org/wiki/Static_random-access_memory)が一般的で、商用では各種の[**Memory Compiler**](https://www.synopsys.com/dw/ipdir.php?ds=dwc_sram_memory_compilers)が用意されている。メモリコンパイラは、動作周波数、ポート数、アドレス幅、データ幅等をパラメータとして入力すると最適なメモリのライブラリ情報を自動生成するツールである。商用メモリコンパイラでは、メモリセル(BitCell)に特別なデザインルールを採用することで必要なシリコン面積を圧縮するものもある。オープン系では[**OpenRAM**](https://openram.org/)が有名で、2ポート(同時に読み書き可能）メモリにも対応している。

### [RDL]()　(**Design Knowledge**)

### [RTL](https://en.wikipedia.org/wiki/Register-transfer_level)　(**Design Standard**)
**Register-transfer level** の略、ロジック回路の抽象的な記述レベル。ラッチ回路などの順序回路に相当する最小の部分を「レジスタ」として抽象化して、ロジック回路の動作を、レジスタからレジスタへの転送とその間の組合せ論理回路によるロジック演算の組み合わせとして記述する。言語仕様として[**Verilog**](https://en.wikipedia.org/wiki/Verilog)や[**VHDL**](https://en.wikipedia.org/wiki/VHDL)が標準化されている。C等の高級ソフトウェア言語と比べると、ロジックゲートや配線等のハードウェアを意識して記述する必要があり、初学者には難しいと感じることも多い。

## 【S - V】

### [SCAN]()　(**Design Knowledge**)

### [SDC](https://www.macnica.co.jp/business/semiconductor/articles/intel/133417)　(**Design Standard**)
**Synopsys Design Constraint**の略。Synopsys社によって開発された設計制約のフォーマット、現在では業界標準になっている。回路が満たすべきタイミング情報（クロックの周期等）を記載する。

### [SERDES]()  (**IPブロック(Hard IP)**)

### [SDF](https://en.wikipedia.org/wiki/Standard_Delay_Format)　(**Design Standard**)
**Standard Delay Format**の略。遅延情報を記述する[IEEE標準フォーマット](https://ieeexplore.ieee.org/document/972829)。パスの遅延時間や遅延時間の制約条件、配線遅延時間なども扱うことができる。

### [SKILL](https://en.wikipedia.org/wiki/Cadence_SKILL)　(**Design Knowledge**)
[**CADENCE**](https://www.cadence.com/en_US/home.html)が提供する（Cadenceに統合される前のSDA社時代からSKILLは存在する）EDA設計ツールにバンドルされたスクリプト言語。基本は[LISP](https://ja.wikipedia.org/wiki/LISP)だが、設計データーベースのオブジェクトへアクセスができるのが特徴（だと理解している）。個人的にはテキストエディタのEmacsとスクリプト言語であるEmacs-Lispの関係と同じだと理解。SKILL言語に精通してCADENCEツールをカスタマイズできるエンジニアを「Skiller(スキラー)」と称するという噂がある。

### [SPI]()　(**IPブロック(Soft-IP)**)

### [SPICE](https://en.wikipedia.org/wiki/SPICE)　(**EDA Methodology/Tool**)
**Simulation Program with Integrated Circuit Emphasis** の略。キルヒホッフの回路方程式を解く回路シミュレーター。1970年代にUC BerkeleyでFORTRAN言語で開発され、SPICE2G6版で実用的に使われるようになった（商用や国内大手が自社開発していたSPICEは、SPICE2G6をルーツにしていた）。商用のSPICEでは、[**HSPICE(Synopsys)**](https://www.synopsys.com/ja-jp/implementation-and-signoff/ams-simulation/primesim-hspice.html)や[**Spector(Cadence)**](https://www.cadence.com/ja_JP/home/tools/custom-ic-analog-rf-design/circuit-simulation.html)がデファクト。オープン系ではC言語に書き直されたSPICE3版がベースの[**Ngspice**](https://ngspice.sourceforge.io/)や、並列化に優れた行列ソルバーを導入した[**Xyce**](https://xyce.sandia.gov/)が有名。フリーのSPICEでは[**LTspice(Analog Device)**](https://www.analog.com/jp/design-center/design-tools-and-calculators/ltspice-simulator.html)が有名。

### [Standard Cell](https://en.wikipedia.org/wiki/Standard_cell)　(**Design Knowledge**)
**SC**とか**スタセル**とか短縮されて呼ばれることが多い。デジタル回路設計用のRTL記述言語([Verilog](https://en.wikipedia.org/wiki/Verilog)や[VHDL](https://en.wikipedia.org/wiki/VHDL))から論理合成ツールを介して最終的にネットとして展開される基本回路（Inverter/NAND/NOR/FF等）群のレイアウトとタイミング(遅延等）情報をまとめたファイル(.lib）を指す。同じ基本回路（例えばInverter)でもネット負荷に応じた駆動能力を持つ複数の素子がライブラリに登録されている。一般にタイミング（遅延）と消費電力はトレードオフの関係にあるので、クリティカルパスを解決するために特別なスタセルを特注・置き換えてタイミングエラーを回避するすることも行われる。また、OAI/AOI等の複合ゲートや、スキャン挿入用のDFF等の特殊回路を登録することも一般的である。

### [STA](https://en.wikipedia.org/wiki/Static_timing_analysis)　(**EDA Methodology/Tool**)
**Static Timing Analysis**の略。タイミング検証方法の一つ。入力から出力（同期回路の場合はFFからFF）までの経路に関して遅延の合計を計算し、**SDC**ファイルに記載された設計タイミング条件を満たされているかどうかを検証する。各経路の最大遅延を合計してセットアップ条件を満たしているか、各部の最小遅延を合計してホールド条件を満たしているか、両者のチェックを行う。[**Prime Time(Synopsys)**](https://www.synopsys.com/implementation-and-signoff/signoff/primetime.html)が商用ではデファクト。オープン系には[**OpenSTA**](https://github.com/The-OpenROAD-Project/OpenSTA)がある。

### [Synthesis](https://en.wikipedia.org/wiki/Logic_synthesis)　(**EDA Methodology/Tool**)
**論理合成ツール**のことを指す。抽象度の高い回路記述であるRTL記述から、**Standard Cell**ライブラリーに登録してあるゲート素子の組み合わせ記述（ネットリスト）に変換する処理及びツール。ソフトウェアの高位言語記述(C言語)を命令セット(ISA)に変換する処理であるコンパイラーに呼応している。商用のツールでは、[**Design Compiler(Synopsys)**](https://www.synopsys.com/implementation-and-signoff/rtl-synthesis-test/design-compiler-graphical.html)や[**Genus/RTL Compiler(Cadence)**](https://www.cadence.com/en_US/home/tools/digital-design-and-signoff/synthesis.html)がある。オープン系では、[**Yosys**](https://yosyshq.net/)が有名→[GitHub](https://github.com/YosysHQ/yosys)

### [Tap Cell](https://ivlsi.com/tap-cell-placement-vlsi-physical-design/)　(**EDA Methodology/Tool**)
チップの基板層（Nwell/Pwell)への電源供給用のセル。適当な間隔で基板へ電源を接続して基板層のインピーダンスを下げて[**ラッチアップ**](https://en.wikipedia.org/wiki/Latch-up)によるチップの破壊を予防する。半導体物理をかじっていないと全く意味不明だが、ひたすらDRCのエラーを消さないと大変なことになる。

### [TO]()  (**Design Knowledge**)

### [UART]()　(**IPブロック(Soft-IP)**)

### [Verilog]()  (**EDA Methodology/Tool**)

### [VHDL]()  (**EDA Methodology/Tool**)

### [WCSP]()  (**Design Knowledge**)

### [WIP]()  (**Design Knowledge**)

### [Wishbone]() (**Design Standard**)

## 【X - Z】
