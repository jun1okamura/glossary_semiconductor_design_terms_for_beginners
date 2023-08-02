# glossary_semiconductor_design_terms_for_beginners
# 半導体初学者むけ「半導体設計で使われる用語集」
※ ぼちぼち更新しています。追加して欲しい用語・略語等あれば連絡ください。

## 【おすすめ動画】

### [【京都賞記念講演】カーヴァー・ミード「情報革命の時代を生きて」](https://www.youtube.com/watch?v=_yjZi83SBZI)
[**Carver Andress Mead**](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%BC%E3%83%90%E3%83%BC%E3%83%BB%E3%83%9F%E3%83%BC%E3%83%89)教授の講演。EDA（集積回路設計ソフト）の生みの親です。チップ設計の歴史を俯瞰して理解することができます。

## 【A - F】

### Analog Hard IP　(**Design Knowledge**)

- [AFE](https://en.wikipedia.org/wiki/Analog_front-end)：
**Analog Front-End** の略。センサー等のアナログ出力信号をデジタル信号へ変換するアナログ回路を指す。一般には、アンプやA/Dコンバータ、フィルタなどのアナログ回路を指すことが多いが、高速シリアル通信向けのクロックが重畳された小振幅信号やPAM(Pulse Amplitude Modulation)信号に変調された信号をデジタル信号に復調するミックスドシグナル回路もAFEと呼ぶことがある。SoC内部にAFEを搭載する場合と、SoCとは別チップでAFEを構成する場合がある。

- [BGR](https://en.wikipedia.org/wiki/Bandgap_voltage_reference)：
**BandGap voltage Reference**の略。正の温度特性を持つPN接合を流れる電流を、負の温度特性を持つ抵抗に流すことで、温度によらずに一定の電圧を発生する、基準電圧回路。SiのBandGap(1.26V)に近い電圧を出力する。回路安定点が２つあり適切なスタートアップ回路が必須である。

- [CDR](https://en.wikipedia.org/wiki/Clock_recovery)：
**Clock and Data Recovery** の略。データとクロックを重畳させたシリアル信号から、受信側でクロック成分とデータ成分を切り分ける回路を指す。送信側では、データに含まれるエッジの場所や数を保証してコード変換(代表的な例として[8b10b](https://ja.wikipedia.org/wiki/8b/10b)エンコードがある)し、受信側では信号に含まれるクロック成分をPLLで同期させることでクロックを抽出、抽出したクロックでデータを復調する。

- [DLL](https://en.wikipedia.org/wiki/Delay-locked_loop)：
**Delay Locked Loop**の略。外部クロックとインバーター（遅延をアナログ的に制御する場合と、量子化された遅延をデジタル的に選択する場合がある）の遅延信号との間で位相をロックをすることで、負の遅延を持ったクロック信号を発生して、セットアップ・ホールドのタイミングマージンを改善できる。同様に外部クロックに対して複数の位相を持った多層クロックを発生したり、数多くの応用回路が提案されている。PLLと比較して、外部クロックの位相の変化に瞬時に追随できる利点がある一方で、PLLの様に、任意の逓倍クロックを発生することは出来ない。

- [LDO](https://en.wikipedia.org/wiki/Low-dropout_regulator)：
**Low Dropout Regulator** の略。ディスクリート部品の三端子レギュレーターの事。チップ内部で使用する電源を、外部から入力された電源から降圧する回路。高電圧側(外部)と降圧電圧(内部)の間に可変抵抗（=トランジスター）を直列に挿入して降圧側の負荷電流に応じて降圧電圧が一定になる様に制御することから、シリーズ・レギュレーターとも言われる。

- [OTP](https://en.wikipedia.org/wiki/Programmable_ROM#One_time_programmable_memory)：
**One Time Programmable memory**の略。一度限り書き込めるメモリブロックIPのことを指す。デバイスのシリアル番号、暗号コード、MACアドレス等のデジタル認識や、ADCやDAC、温度センサー等の校正データー、メモリの冗長セル置き換え等に使われる。昔はレーザーで物理的に加工(レーザートリム)していたが、電気的に、MOSトランジスターのVthを変えたり、破壊したりする方式が主流になっている。

- [PLL](https://en.wikipedia.org/wiki/Phase-locked_loop)：
**Phase Locked Loop**の略。VCO（Voltage Controlled Oscillator)、PD(Phase Detector)とLP(LoopFilter)により構成される。外部クロックをM分週した信号と自走するVCOからN分週した信号をPDで比較することで、外部クロックに対して、N/M倍の周波数のクロックを発生できる。また、N倍とN＋1倍を交代選択することで外部クロックで割り切れない周波数を発生する [Fractional PLL](https://www.electronics-notes.com/articles/radio/frequency-synthesizer/pll-indirect-digital-fractional-n-synthesis.php) もある。クロック発振機以外の応用として、CDRのビルディングブロックや、RF信号の復調、クロック信号のデスキューやノイズの除去、EMI対策向けのSSCG(スペクトラム拡散クロック発生器）等、多くの応用がある。PLLの設計は、応用に必要な動的な特性を、構成する部品の静的な特性設計により満たすことであり、特性間の時間刻みの隔たりが大きいのでトップダウン的な設計が求められる。またPLLからのクロックの位相ノイズの検証は、PSS解析シミュレーターとモデルが必要になる。
    
### [BUS](https://en.wikipedia.org/wiki/Bus_(computing))　(**Design Standard**)
一つの通信経路に対して、複数のデバイスが接続されるバス・トポロジーを構成する通信経路方式のこと。一対一（ピアツーピア）の接続の場合はバスと呼ばずにチャネルと呼ぶ。

#### [AMBA](https://en.wikipedia.org/wiki/Advanced_Microcontroller_Bus_Architecture)
**Advanced Microcontroller Bus Architecture**の略。チップ内部のIP間のバスインターフェース規格。IP間で valid/ready のハンドシェイク動作をして有効データを判断する。APB＞AHB＞AXIの順で進化した。
- [APB](https://en.wikipedia.org/wiki/Advanced_Microcontroller_Bus_Architecture#Advanced_Peripheral_Bus_(APB))：
**Advanced Peripheral Bus**の略。ARM により[定義された](https://developer.arm.com/documentation/ihi0024/c/)低速の32bitバス規格。
  
- [AHB](https://en.wikipedia.org/wiki/Advanced_Microcontroller_Bus_Architecture)：
**Advanced High-performance Bus**の略。ARM により[定義された](https://developer.arm.com/documentation/ihi0011/a/)(64/128/256/512/1024)bitバス規格。

- [AXI](https://en.wikipedia.org/wiki/Advanced_eXtensible_Interface)：
**Advanced eXtensible Interface**の略。ARM により[定義された](https://developer.arm.com/documentation/ihi0022/latest/)インターフェース仕様。チャネルの概念が導入された。

#### [Wishbone](https://en.wikipedia.org/wiki/Wishbone_(computer_bus))
オープンIPの流通組織 [**OpenCores**](https://opencores.org/) がIP間接続のために規定したオープンソースの[バス規格](https://github.com/fossi-foundation/wishbone)のこと。8/16/32/64ビット幅のMaster-Slave接続。

#### [NOC](https://en.wikipedia.org/wiki/Network_on_a_chip)
**Network On Chip** の略。複数の速度の異なるIP間通信が必要なSoCチップ設計において、通信を一旦パケット化することで、速度や頻度の異なるIP間通信を効率的に処理することを目的に考案された。例えば、AXIフォーマットのIP間通信をNOCのパケットに変換して送受信できる。コンピューター間で行われていた広域ネットワーク通信の概念をチップ内のIP間の通信に適用したもの。

### [EDA Design Flow](https://en.wikipedia.org/wiki/Design_flow_(EDA))  (**EDA Methodology/Tool**)
チップ設計(一般にはRTLからGDSIIまで)に必要なEDAツールの組み合わせと一連の流れを指す。オープンソースなEDAツールで構成された[OpenLane](https://openlane.readthedocs.io/en/latest/)が整備されたことで、商用のツールを使わずにロジックチップを設計する環境が整い始めた。

- [Synthesis](https://en.wikipedia.org/wiki/Logic_synthesis)：
**論理合成ツール**のことを指す。抽象度の高い回路記述であるRTL記述から、**Standard Cell**ライブラリーに登録してあるゲート素子の組み合わせ記述（ネットリスト）に変換する処理及びツール。ソフトウェアの高位言語記述(C言語)を命令セット(ISA)に変換する処理であるコンパイラーに呼応している。商用のツールでは、[Design Compiler](https://www.synopsys.com/implementation-and-signoff/rtl-synthesis-test/design-compiler-graphical.html)(Synopsys)や[Genus/RTL Compiler](https://www.cadence.com/en_US/home/tools/digital-design-and-signoff/synthesis.html)(Cadence)がある。オープン系では、[**Yosys**](https://yosyshq.net/)+[**ABC**](https://people.eecs.berkeley.edu/~alanmi/abc/) が有名→[GitHub-Yosys](https://github.com/YosysHQ/yosys), [GitHub-ABC](https://github.com/berkeley-abc/abc)

- [STA](https://en.wikipedia.org/wiki/Static_timing_analysis)：
**Static Timing Analysis**の略。タイミング検証方法の一つ。入力から出力（同期回路の場合はFFからFF）までの経路に関して遅延の合計を計算し、**SDC**ファイルに記載された設計タイミング条件を満たされているかどうかを検証する。各経路の最大遅延を合計してセットアップ条件を満たしているか、各部の最小遅延を合計してホールド条件を満たしているか、両者のチェックを行う。[Prime Time](https://www.synopsys.com/implementation-and-signoff/signoff/primetime.html)(Synopsys)が商用ではデファクト。オープン系には[**OpenSTA**](https://github.com/The-OpenROAD-Project/OpenSTA)がある。

- [DFT](https://en.wikipedia.org/wiki/Design_for_testing)：
**Design For Testing** or **Design For Testability**の略。日本語だと「テスト容易化設計」であるが、言い換えると「LSIのテストの実行を容易にするための回路設計手法」の総称を指す。具体的には、テストモードとしての独自機能を備えたLSI、セルフテスト回路を設けたLSI、論理回路のテストのためのスキャンパスを設けたLSI、CMOSの暗電流に着目したテスト手法、等々がある。採用する手法、技術と必要なシリコン面積等のオーバーヘッドと、テスト容易化で得られるテストコスト削減効果のバランスが重要である。

- [P&R/PnR](https://en.wikipedia.org/wiki/Place_and_route)：
**Place and Route**の略。**APR**(Automatic Place & Route)とも呼ぶ。日本語だと**配置配線**工程のこと。ゲートレベルのネットリストから、対応するスタンダードセルをチップ上のどこに置くかを決定する配置作業。これに続いてセル同士を結ぶ配線層で結ぶ配線作業を担うツールおよび作業工程のこと。論理合成までをフロントエンドもしくは論理設計、P&R以降のレイアウト作業をバックエンドもしくは物理設計と呼ぶ場合が多い。商用ツールでは[IC compiler](https://www.synopsys.com/ja-jp/implementation-and-signoff/physical-implementation/ic-compiler.html)(Synopsys)や、[Innovus](https://www.cadence.com/ja_JP/home/tools/digital-design-and-signoff/soc-implementation-and-floorplanning/innovus-implementation-system.html)(Cadence)がある。

- [CTS](https://ivlsi.com/clock-tree-synthesis-cts-vlsi-physical-design/)：
**Clock Tree Synthesis** の略。同期設計においてはフリップフロップへ供給される同期クロックの位相が完全に一致していることが望ましいが、同期クロック信号は、一番負荷が重く、配線長も長いことから、チップ内に分散されたフリップフロップに供給している同期クロック信号の位相を合わせる為には、特別な手当をする必要がある。具体的には、クロックバッファーの挿入やクロック配線の引き回し等により、消費電力とタイミング（最大動作周波数）の最適化を図る設計工程を指す。動作処理性能が最優先されるCPUやメモリ設計では、ツールに任せずに、人手でクロック配線とバッファーの配置を設計することもある。

- [DFM](https://en.wikipedia.org/wiki/Design_for_manufacturability)：
**Design For Manufacturability**の略。半導体設計におけるDFMは、製造されたチップの歩留まり率(Yield)を上げる為に行われる設計段階での工夫のことを総称する。DFMツールは、ポリ・メタル挿入(CMPでのDishing対策）、ダブルVIA挿入(VIAのオープン対策)、配線拡張（配線切れ対策）などを行うツールである。リソグラフィーの解像度を改善する(OPC=Optical Proximity Correction：光学近接効果補正)為の補助パターン挿入ツールも広義のDFMツールに含まれる。またメモリの冗長回路・ECC回路の採用、カスタムレイアウト設計で「最小寸法をなるべく避ける」等も広義のDFMに含まれる。

- [ECO](https://en.wikipedia.org/wiki/Engineering_change_order)：
**Engineering Change Order**の略。P&R等の物理設計が完了したデザインの最終段階での回路変更を、一般にECOと呼ぶ。**pre-mask ECO**(Standard Cellの置き換えあり)と**post-mask ECO**(未使用のStandard Cell(ECO用セル)だけをつかう)に区別して使う場合もある。設計フローの上流に戻らずに、デザイン機能の変更やバグ修正を配線と未使用のStandard Cell(置き換えやECO用セル)を利用して実現する手続きのこと。ECOをサポートするツールもある。

- [Formal Verification](https://en.wikipedia.org/wiki/Formal_verification)：
半導体設計における **Formal Verification** (形式的検証)とは、回路記述間を数学的に解析することで，記述間(例えばRTL記述とゲート記述)の論理が等価であるかどうかの検証（等価性検証）や、回路記述が動作性能に関する記述を満たしているかの検証（プロパティ検証）がある。シミュレータのように回路を動作させて検証するのではないので、シミュレーション・パターンの作成が不要で，かつ高速・網羅的に検証できるというメリットがある。

### [File Format](https://en.wikipedia.org/wiki/File_format)　(**Design Standard**)
EDAツールで使われるファイルフォーマットを説明する。

- [CDL](https://en.wikipedia.org/wiki/Circuit_design_language)：
**Circuit Design Language** の略。SPICE向けネットリストからモデル情報を除た LVS や LPE の為に使われるファイルフォーマット。

- [GDSII](https://en.wikipedia.org/wiki/GDSII)：
**Graphic Design System II**の略。1970年末に商用化されたLayout設計装置([Calma](https://en.wikipedia.org/wiki/Calma))が採用したファイルフォーマット。最近だと[GDSFACTORY](https://gdsfactory.github.io/gdsfactory/index.html)等のオープンソースなツールもある。

- [LIB](https://en.wikipedia.org/wiki/Standard_cell)：
**Liberty Timing Format** 記述のファイル(.lib)を指す。**Standard Cell**ライブラリの遅延/消費電力などの特性を記述したファイル。微細化に伴い、ばらつきに対応した拡張フォーマットには CCS(Composite Current Source)やECSM(effective current source model)などがある。遅延情報はSDF(Standard Delay Format: IEEE std 1497-2001)を用いてネットリストの各ネットにバックアノテートされる。

- [MEBES](https://www.layouteditor.org/layout/file-formats/mebes)：
**Manufacturing Electron Beam Exposure System**の略。[EtecSystem](https://en.wikipedia.org/wiki/Etec_Systems)の電子線描画装置向けのファイルフォーマット。露光用のマスクは GDSII レイアウト情報から MEBES フォーマットへ変換して作製する。

- [SDC](https://www.macnica.co.jp/business/semiconductor/articles/intel/133417)：
**Synopsys Design Constraint**の略。Synopsys社によって開発された設計制約のフォーマット、現在では業界標準になっている。回路が満たすべきタイミング情報（クロックの周期等）を記載する。

- [SDF](https://en.wikipedia.org/wiki/Standard_Delay_Format)：
**Standard Delay Format**の略。遅延情報を記述する[IEEE標準フォーマット](https://ieeexplore.ieee.org/document/972829)。パスの遅延時間や遅延時間の制約条件、配線遅延時間なども扱うことができる。

## 【G - L】

### General (Better to know)　(**Design Standard**)
半導体設計で良く使われる用語をまとめています。

#### [ATPG](https://en.wikipedia.org/wiki/Automatic_test_pattern_generation)
**Automatic Test Pattern Generation**の略。設計したチップのテストに必要なテストプログラムを自動で生成する方法およびツールのこと。ネットリストを読み込み、不良モデルを仮定してテストパターンを自動合成するツール。

#### [BIST](https://en.wikipedia.org/wiki/Built-in_self-test)
**Buit-in Self TEST**の略。設計した回路の動作チェックを内蔵したテスト用の回路を使ってテストすること。費用のかかる半導体専用テスターを使わずに合否を判定する。内蔵メモリのテストに使われることが多いが、メモリ以外にもAFE回路等の半導体専用テスターではテスト出来ない回路のテストの為に利用される。

#### [CSR](https://en.wikipedia.org/wiki/Control/Status_Register)
**Control Status Register** の略。CPUの計算処理の結果フラグ（オーバーフローとかキャリーとか）や動作モード（スーパバイザとかユーザー）、状態（割込やトラップ）状態が格納されるレジスターのこと。

#### [Emulator](https://en.wikipedia.org/wiki/Hardware_emulation)
エミュレータは，ロジック回路をFPGAや専用ハード等にマッピングして，その回路の動作を高速に実行する装置のこと。シミュレーターでは評価することが難しい画像や音声の品質等の検証や、OSのブートシーケンス等の長い時間がかかる検証に使われる。[Palladium](https://www.cadence.com/en_US/home/tools/system-design-and-verification/acceleration-and-emulation/palladium-z1.html)(Cadence)や[Zebu](https://www.synopsys.com/verification/emulation/zebu-empower.html)(Synopsys)、[Veloce](https://eda.sw.siemens.com/en-US/ic/veloce/)(Siemens)等がある。一般に大変高価な装置なので、複数の大型FPGAの組み合わせで代用することもあるが、その場合ネットに手を加えると厳密な検証にはならないデメリットもある。

#### [ESD](https://en.wikipedia.org/wiki/Electrostatic_discharge)
**ElectroStatic Discharge**の略。静電気によるチップの破壊およびその対策回路・評価方法・基準のことを指す。HBM(Human Body Model)やCDM(Charged Device Model)等の基準がある。適切にESD素子を配置しないと製品に必要なESD基準を満たすことができない。RFやSerDes等の高速信号を扱う製品ではESDに特別な工夫が必要になる。

#### [GA](https://en.wikipedia.org/wiki/Gate_array)
**Gate Array**の略。チップ全面にトランジスターを敷き詰めたWaferを用意して在庫しておき、配線層だけでロジックチップを製造する方法。0.35um世代ごろまでASICといえばGAが主流だった。

#### [IBIS](https://en.wikipedia.org/wiki/Input/output_Buffer_Information_Specification)
**Input/output Buffer Information Specification** の略。PCBボード上のLSIチップ間の接続をシミュレーターにて検証する際に利用されるIOの特性モデル。実際のIOの回路を電圧電流源やRLC回路でモデル化することで、複数ベンダーのチップ間のPCBボードを含む信号品質やタイミング検証が可能となる。

#### [JTAG](https://en.wikipedia.org/wiki/JTAG)
**Joint Test Action Group** の略。業界標準のテスト手法、PCBの基板検査のための標準規格から始まった。インタフェースの仕様は[IEEE1149.1](https://www.ti.com/lit/an/ssya002c/ssya002c.pdf)で定められているが、実際には半導体メーカーがプライベート命令やオプションレジスタを使って拡張している為に「総合デバッグインタフェース」になっている。TCK/TDI/TDO/TMSの4線とTRSTの5線を使う場合がある。FPGAの書き込みや、CPUのデバッグ、基板検査、ICの内部回路のテスト等に使われる。

#### [KGD](https://xtech.nikkei.com/dm/article/WORD/20090121/164414/)
**Known Good Die** の略。良品のベア・チップを指す通称。複数のチップを1つのパッケージに収めるMCP(Multi-Chip Package)やチップレット，縦に積んだ複数のチップ間を貫通電極で接続する3次元実装などでは，実装する前に良品チップであることが保証されていないと、実装後の不良品が多く発生する問題がある。チップを提供する側と実装する側は、相反するコスト分担関係にある為に、KGD自体の動作保証レベル・品質保証レベルに関しては個別の対応されている。

#### [Master/Slave](https://en.wikipedia.org/wiki/Master/slave_(technology))
デバイス間の接続関係の総称。ハードウェアだけでなくソフトウェアでの実装でも使われる。2020年頃より差別的な用語の見直しが広がり、ホスト/クライアントやMain/Secondary(M/Sが使えるから）との言い回しを使うようになっている。ホスト側デバイスがクライアント側デバイスに出した指示に応じて、クライアント側デバイスが応答する接続関係。

#### [MiM/MoM]()
**Metal Insulator Metal/Metal Oxide Metal**の略。半導体設計で容量素子というとMOSトランジスターのゲート容量を使うことが一般的だが、容量値の電圧や温度依存性が大きい事が課題であり、そのような課題を解決するためにゲートPolySiの他に対抗電極用にもう一枚PolySiを導入してPoly-Polyの容量素子が使われて来たが、近年、素子の微細化と多層配線化に伴い、メタル配線層を組み合わせて容量素子として使うMiM/MoMが主流となっている。

#### [PDN](https://en.wikipedia.org/wiki/Power_integrity)
**Power Distribution Network**の略。電源ネットワークの事であり、電源ネットワークによって決まる電源インピーダンスのことを指す。チップ内部の電源ネットワークに加えて、パッケージやチップ近傍のPCBの電源配線や平滑容量の配置等も考慮する場合がある。電源電圧の局所的なドロップは回路の動作不良を導くので、必要に応じてPDNを補強することが求めれれる。また、チップの入出力信号の品質をSignal Integrity(SI)と呼び、電源インピーダンスと電源ドロップの品質をPower Integrity(PI)と呼ぶ。SI/PIは相互にとても関係が深い。

#### [SKILL](https://en.wikipedia.org/wiki/Cadence_SKILL)
スクリプト言語。CADENCE のEDA設計ツールにバンドルされている。基本は[LISP](https://ja.wikipedia.org/wiki/LISP)だが、設計データーベースのオブジェクトへアクセスができるのが特徴。テキストエディタのEmacsとスクリプト言語であるEmacs-Lispの関係と同じ。SKILL言語に精通してCADENCEツールをカスタマイズできるエンジニアを「Skiller(スキラー)」と称するという噂がある。

#### [SSO/SSN](https://en.wikipedia.org/wiki/Ground_bounce)
**Simultaneous Switching Output/Simultaneous Switching Noise**の略。複数の出力が同時にスイッチング動作をすることで、電源にスパイク電流が流れること及びそれによるノイズの発生を指す。幅の広いパラレル信号（データバス等）で特に問題となる。

#### [TCL](https://en.wikipedia.org/wiki/Tcl)
スクリプト言語。1980年代 **Magic** のスクリプト機能の拡張の為に開発された。商用の Synthsis ツールである DesignCompiler でもスクリプト言語として TCL を採用したことから EDA 業界のスクリプト言語として根付いている。

#### [TO](https://en.wikipedia.org/wiki/Tape-out) 
**Tape Out**の略。半導体開発における**TO**は、設計・検証が完了してGDSIIフォーマットのレイアウトデータをマスク変換(MEBESフォーマット)する組織（マスクハウスや前工程ファブ）に送付すること。TO前の最終検証を**Sign-Off**手続きと呼ぶ。

### [Hardware Description Language](https://en.wikipedia.org/wiki/Hardware_description_language)  (**EDA Methodology/Tool**)
ハードウェア記述言語(HDL)は、電子回路の記述形式であり、回路解析やシミュレーションをしたり、HDL記述からネットリストに変換や合成をし、配置配線してチップを作成するためのレイアウトデーターに変換する為に考案された。プログラミング言語の様に、式、文、制御構造からなるテキスト記述であるが、HDLには時間の概念が含まれていることに大きな違いがある。以下、レジスタを言語上で定義するのがRTL、処理系が割り当てるのがHLSと区別した。

#### [RTL](https://en.wikipedia.org/wiki/Register-transfer_level)
**Register-Transfer Level** の略、ロジック回路の抽象的な記述レベル。ラッチ回路などの順序回路に相当する最小の部分を「レジスタ」として抽象化して、ロジック回路の動作を、レジスタからレジスタへの転送とその間の組合せ論理回路によるロジック演算の組み合わせとして記述する。C等の高級ソフトウェア言語と比べると、ロジックゲートや配線等のハードウェアを意識して記述する必要があり、初学者には難しいと感じることも多い。

- [Verilog](https://en.wikipedia.org/wiki/Verilog) 代表的なRTL言語[**IEEE 1364-2005**](https://ieeexplore.ieee.org/document/1620780)として標準化されている。最新版であれば規格書を無料で入手できる。

- [Verilog-AMS](https://en.wikipedia.org/wiki/Verilog-AMS) ミックスドシグナル拡張（AMS）を含む Verilog の[**拡張言語仕様**](https://www.accellera.org/images/downloads/standards/v-ams/VAMS-LRM-2-4.pdf)

- [SystemVerilog](https://en.wikipedia.org/wiki/SystemVerilog) 検証系の機能が追加された Verilog の拡張言語[**IEEE 1800-2017**](https://ieeexplore.ieee.org/document/8299595)として標準化されている。最新版であれば規格書を無料で入手できる。

- [VHDL](https://en.wikipedia.org/wiki/VHDL) 代表的なRTL言語[**IEEE 1076-2019**](https://ieeexplore.ieee.org/document/8938196)として標準化されている。最新版であれば規格書を無料で入手できる。

- [Chisel](https://www.chisel-lang.org/) 
UC berkeleyが開発した新しいハードウェア設計言語。モジュールからRTLを自動生成もできる。

#### [HLS](https://en.wikipedia.org/wiki/High-level_synthesis)
**High-Level Synthesis** の略。RTL記述よりさらに抽象度を上げた記述からロジック回路を設計する手法。

- [SystemC](https://en.wikipedia.org/wiki/SystemC) システム設計・ハードウェア設計向けの C++ クラスライブラリ。

- [XLS](https://github.com/google/xls) Googleが開発しているオープン系のHLS等

### Interface IP　(**Design Standard**) 

- [DDR](https://en.wikipedia.org/wiki/Double_data_rate)：
**Double Data Rate**の略。転送クロックの両エッジでデータを転送することで2倍の転送速度を可能にする通信方式を指すが、DRAM(SDRAM)とのインターフェースとして標準化されて以来、DDRというとDRAM用のインターフェースを指すことが多い。[JEDEC](https://www.jedec.org/standards-documents/docs/jesd-79f)で標準化されている。
  
- [GPIO](https://en.wikipedia.org/wiki/General-purpose_input/output)：
**General Purpose Input/Output**の略。文字通り汎用IO回路、入出力設定、ドライブ電流調整、プルアップ・プルダウン、トライステート機能等が、ソフトウェアやレジスターにて設定できる。一般にはGPIOピンは、低速インターフェースやアナログ入出力と兼ねる場合が多い。

- [I2C](https://en.wikipedia.org/wiki/I%C2%B2C)：
**Inter-Integrated Circuit** の略。SDAとSCLのフィリップス社で開発された２線デジタルインターフェース。転送スピードは100K/400KHz、プルアップ抵抗でLo-Hiをドライブする仕様の為に高速動作や長距離伝送は難しい。通信に必要な信号線が少ないことと、回路規模が小さいことから、多くのセンサーやAD/DAコンバーター、ファン制御、小型LCDパネル、LEDアレー等で使われている。アイ・スクェアード・シーもしくはアイ・ツー・シーと呼ぶ。

- [I2S](https://en.wikipedia.org/wiki/I%C2%B2S)：
**Inter-IC Sound** の略。デジタルPCM信号(音声)向けのフィリップス社で開発されたデジタルインターフェース。BCLK/LRCLK/DATAの3線で接続する場合とMCLKを加えた4線で接続する場合がある。2チャンネルのステレオ対応のI2Sを多チャンネルに拡張したTDM(Time Division Multiplexing)フォーマットもある。IISとは略さないので注意。

- [LVDS](https://en.wikipedia.org/wiki/Low-voltage_differential_signaling)：
**Low-Voltage Differential Signaling**の略。[ANSI/TIA/EIA-644](https://www.tij.co.jp/jp/lit/ug/jajd001/jajd001.pdf?HQS=ti-null-null-tedfaq_if-jp)
で標準化された小振幅差動伝送方式のこと。LVDSは信号の電気的な規格のことだが、高速伝送のIOを総称する場合もある。特に液晶パネルとメイン基板との間の画像向け通信規格としてLVDS＋SerDes(７逓倍データレート)がデファクトとして長い間使われてきたことから、LVDSと言うと液晶パネルとの画像通信規格と理解している人も多い。

- [PCIe](https://en.wikipedia.org/wiki/PCI_Express)：
**PCI-Express**のこと、PCIは(Peripheral Component Interconnect)のことで、インテルが1992年に提唱したPCマザーボード上のバス規格。PCI(32bit/33MHz)がルーツで、CPUの32bit化を契機にそれまでのISA(Industrial Standard Architecture)バスから置き換えられた。インテルは[PCI-SIG](https://pcisig.com/)による標準化を進めた為に、業界標準として広く利用されるようになった。高速転送を実現する為に、それまでのパラレル伝送方式から SerDes＋CDR のシリアル伝送方式に変更した為にPCIに**express**が加えられてPCIeと呼ぶ規格になった。

- [UCIe](https://en.wikipedia.org/wiki/UCIe)：
**Universal Chiplet Interconnect Express**の略。2022年に、AMD/Arm/ASE Group/Google-Cloud/Intel/Meta/Microsoft/Qualcomm/Samsung/TSMC により立ち上げられたチップレット間の高速SerDes通信規格とその[標準化組織](https://www.uciexpress.org/)のこと。
   
- [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface#Intelligent_SPI_controllers)：
**Serial Paralel Interface**の略。一般にはSCLK/MOSI/MISO/CSの4線を使った全二重シリアル通信方式を指す。I2Cと比較してピン数が増える代わりに、高速に全二重通信できるメリットがあり、CPUやFPGA等のプロセッサーチップと外部との通信向けに採用される。

- [QSPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface#Quad_SPI)：
**Quad SPI**の略。SPIの4線にSIO2とSIO3の2線を加えて、半二重で4倍のデータを通信できるようにしたSPIの拡張規格。フラッシュメモリ等の外部メモリとの接続に使われることが多い。

- [SerDes](https://en.wikipedia.org/wiki/SerDes)：
**Serializer DeSerializer**の略。広義にはパラレルーシリアル変換とその逆変換のことを指すが、高速シリアル通信技術を総称してSerDesと言うことが多い。技術的には **Source Synchronous Clocking** と **Embedded Clocking** 方式に大きく分けられる。通信経路での信号の劣化を抑える為にコード変換したり、擬似ランダム信号によるスクランブルをかけて信号帯域を制限する。またトレーニングシーケンスを導入してケーブルの品質や長さの違いを自動的に補償することも行われる。前者の代表は HDMI、後者の代表は PCIe 等がある。
  
- [UART](https://en.wikipedia.org/wiki/Universal_asynchronous_receiver-transmitter)：
**Universal Asynchronous Receiver Transmitter**の略。非同期シリアル通信方式（つまりクロックは伝送しない）TXとRXによる全二重通信を行う。クロックは送受信側で独立クロックを使うので、通信をする前に双方のデータ転送速度や規格（ボーレートやストップビット等）を合わせておく必要がある。受信側では受信したデータをオーバーサンプルすることで、送受信端で異なるクロックソースの誤差を吸収する。昔は大型コンピューターと端末の間の通信として使われたので RS232 や RS422 規格に電気的に変換して長距離接続に対応していた。
  
- [USB](https://en.wikipedia.org/wiki/USB)：
**Universal Serial Bus**の略。PCの周辺機器接続用インターフェースとしてCompaq/DEC/IBM/Intel/Microsoft/NEC/Nortelにより1995年に提唱された。[USB-IF](https://www.usb.org/)による標準化を進めた為に、業界標準として広く利用されるようになった。外部機器(最初はマウス)用に電源を供給できる先駆けとなったインターフェースである。また Plug-and-Play を実現する為に、ソフトウェア階層とデバイス側レジスターの標準化を進めたことも特徴的。今では当然だが、外部機器向けのドライバーをインストールしなくてもUSBを挿すだけで使えるようになった影には、世界中のエンジニアの多くの知恵と努力が重ねられている。
  
## 【M - R】

### Manufacturing-related Terminology　(**Design Knowledge**)

- [CMP](https://en.wikipedia.org/wiki/Chemical-mechanical_polishing)：
**Chemical Mechanical Polishing**の略。半導体設計でのCMPとは、各プロセスステップ毎にWafer表面を化学薬品(スラリー)と微細なやすり(パット)により平坦化する工程のこと、ゴミを嫌うクリーンルームには馴染まないプロセス方式だが、微細化が進み焦点深度が浅くなった露光機でパターンを現像する為にブレークスルーとなった技術。パターンが無い領域や広い領域が皿状に削られる(Dishing)を防ぐ為に、DFM工程にてFillパターンやスリットが挿入される。  
  
- [Edge Seal](https://ir.nctu.edu.tw/bitstream/11536/13376/1/000232253500007.pdf)
チップを分割するダイシング領域とチップ本体との間に設けられる特別な構造を指す。一般には、コンタクト/Viaと配線層を壁状に構成する。ダイシング時に発生する層間膜のクラックがダイシング領域からチップ本体内部に成長することを防ぐ。

- [FEOL](https://en.wikipedia.org/wiki/Front_end_of_line)/[BEOL](https://en.wikipedia.org/wiki/Back_end_of_line)：
半導体の製造工程において、トランジスターを作るまでの工程を**FEOL**といい、トランジスターを結ぶ配線層の工程を**BEOL**という。

- [GAA](https://en.wikipedia.org/wiki/Multigate_device#GAAFET)
**Gate-All-Around FET**の略。一般にMOSトランジスターはWafer表面にチャネル層を形成しチャネルに対抗したゲート層でチャンネルを抵抗を変調することで動作する。Wafer表面を使うMOSトランジスターを**PlanerFET**という、表面を凸凹状に加工してチャネル長を確保しつつ更に微細化(~16nm以降)したMOSトランジスターを**FinFET**という、チャネルをゲート層で海苔巻状に囲って３次元に積層した(~2nm以降)MOSトランジスターを**GAAFET**という。

- [OPC](https://en.wikipedia.org/wiki/Optical_proximity_correction)：
**Optical Proximity Correction**の略。半導体設計でのOPCとは、露光波長近くのパターンを現像する為に、元のレイアウトデーターを補正する工程およびツールのことを指す。ちなみに、露光波長より更に細かいパターンを現像する為に、異なるマスクで2度露光することをダブルパターニングと呼ぶ。

- [MCM](https://en.wikipedia.org/wiki/Multi-chip_module)：
**Multi-Chip Module**の略。半導体設計でのMCMとは、複数にチップを一つのパッケージに封入することを指す。パワー半導体＋コントローラーやメモリ＋CPU等をMCMとしてインナーフレームやボンディングで接続したことから始まり。最近は、CIS＋コントローラーを３D積層したチップ、Siインターポーザーでチップ間を高速通信チャネルで接続するチップレット技術に進化している。

- [RDL](https://en.wikipedia.org/wiki/Redistribution_layer)：
**ReDistribution Layer**の略。半導体設計でのRDLとは、CSPパッケージ向けの再配線層のことを指す。

- [WIP](https://en.wikipedia.org/wiki/Work_in_process)：
**Work In Process**の略。半導体設計でのWIPとは、チップがどの工程にあるのか？を言う場合が多い。
  
### [Package](https://en.wikipedia.org/wiki/Electronic_packaging)　(**Design Knowledge**)
挿入型のDIPから表面実装型のQFPへ進化、フットプリントの縮小でQFNが生まれ、CSPへ進化した。QFP/QFN の頭に、"L","T"を付けて薄型のパッケージ仕様を表す。

- [DIP](https://en.wikipedia.org/wiki/Dual_in-line_package)：
**Dual In-line Package**の略。1970-80年代ICのパッケージといえばDIPでした。

- [QFP](https://en.wikipedia.org/wiki/Quad_flat_package)：
**Quad Flat Package**の略。4方向にリード端子のあるパッケージ。二方向にしかリード端子のないパッケージはSOPと呼ぶ。

- [QFN](https://en.wikipedia.org/wiki/Flat_no-leads_package)：
**Quad-Flat No-leads**の略。4方向に端子のあるリードがないパッケージ。二方向にしかリード端子のないパッケージはDFNと呼ぶ。

- [CSP](https://en.wikipedia.org/wiki/Chip-scale_package)：
**Chip Scale Package** チップサイズと同等まで縮小したパッケージ。特にチップ内の端子とパッケージの端子との接続を、ボンディングではなく **RDL(再配線層)** を、Wafer状態で設けて半田ボールと直に接続するパッケージを **WCSP** と呼ぶ。

### [PDK](https://en.wikipedia.org/wiki/Process_design_kit#)　(**Design Knowledge**)
**Process Design Kit** の略。半導体プロセスに依存した設計に必要な設定情報一般の呼称。設計ツール毎に必要な、Technology file 群（Spice model や DRC/LVS の runset、Layer ファイル等）と、回路設計に必要な、回路Symbolや、基本Library(IO や Standard Cell, Pcell, SRAM 等）に大きく分けられます。実態を理解せずに概念的にPDKという単語を使う人もいるので注意。

### [Pysical Verification](https://en.wikipedia.org/wiki/Physical_verification)　(**EDA Methodology/Tool**)

- [DRC](https://en.wikipedia.org/wiki/Design_rule_checking)：
**Design Rule Checking** の略。半導体プロセスの加工工程における物理的な寸法や公差から決められた設計制約の検証作業。PCBのパターン設計でのDRCと基本は同じ。最先端プロセスになるほどに設計制約は増加するので、DRCに必要なルールファイルは複雑化し実行時間も増加している。80年代、1umルールの頃は手書したレイアウト図面をミニコンでDRCを実行し、数十センチにもなるラインプリンター紙に出力されたエラーを一つ一つ人手で修正していた時代もあった。

- [ERC](https://en.wikipedia.org/wiki/Physical_verification#Electrical_Rule_Check_(ERC))：
**Electrical Rule Check** の略。電源ショートやフローティング信号、短絡信号等の電気的に致命的なルールのチェック。ラッチアップやESD関連のルールをチェックしたり、アンテナ現象(プラズマ系加工プロセスでの帯電によるゲート酸化膜の破壊対策）をチェックする場合もある。

- [LPE](https://en.wikipedia.org/wiki/Parasitic_extraction)：
**Layout Parasitic Extraction** の略。レイアウト情報から回路図には明示的に記述されていない寄生素子（RLC）を抽出して[SPICE](https://en.wikipedia.org/wiki/SPICE)等のネット情報として出力するツール。膨大な数の寄生素子が出力されることで回路シミュレーションが実行できないという課題に対応するために、寄生素子を電気的に等価な記述に圧縮記述する機能がある。ロジック設計ではネットの遅延情報としてフィードバックされる。

- [LVS](https://en.wikipedia.org/wiki/Layout_Versus_Schematic)：
**Layout Versus Schematic** の略。回路図とレイアウトの比較検証作業。回路図から抽出したネット情報とレイアウトから抽出したネット情報の等価性チェック。[SPICE](https://en.wikipedia.org/wiki/SPICE)や[CDL](https://en.wikipedia.org/wiki/Circuit_design_language)記述のネットを使って等価検証を行う。手書きの回路図しか無かった80年代では、人手でレイアウトの逆読みと手書き回路図との比較をダブル・トリプルに検証していた時代もあった。

- Tools

  - [Magic](http://bwrcs.eecs.berkeley.edu/Classes/IcBook/magic/)は、1983年UCB校で開発されたオープンソースのレイアウトツールであり、OpenLaneのDRCツールとして使われている。

  - [Calibre](https://eda.sw.siemens.com/en-US/ic/calibre-design/)は、Siemens社の大規模回路に対応したDRC/LVS/LPEの事実上の商用デファクトツール。

### [RAM generator](https://soclabs.org/design-flow/memory-generators)　(**Design Knowledge**)
LSIに内蔵されるメモリは[**SRAM**](https://en.wikipedia.org/wiki/Static_random-access_memory)が一般的で、商用では各種の[**Memory Compiler**](https://www.synopsys.com/dw/ipdir.php?ds=dwc_sram_memory_compilers)が用意されている。メモリコンパイラは、動作周波数、ポート数、アドレス幅、データ幅等をパラメータとして入力すると最適なメモリのライブラリ情報を自動生成するツールである。商用メモリコンパイラでは、メモリセル(BitCell)に特別なデザインルールを採用することで必要なシリコン面積を圧縮するものもある。オープン系では[**OpenRAM**](https://openram.org/)が有名で、2ポート(同時に読み書き可能）メモリにも対応している。

## 【S - V】

### Sample (**Design Knowledge**) 
開発チップは、ES>CS>MP の順でステータスが上がる。
- [**ES**](https://semicon.jeita.or.jp/word/word.html)：
**Engineering Sample** の略。機能評価＋テスト開発＋ソフト開発＋信頼性試験等の社内・パートナーでの評価用チップ。

- [**CS**](https://semicon.jeita.or.jp/word/word.html)：
**Commercial Sample** の略。顧客評価用サンプルのこと、量産する前に顧客を限定して配布（販売）するチップのこと。

- [**MP**](https://semicon.jeita.or.jp/word/word.html)：
**Mass Production** の略。量産版のチップのこと。MPと呼ばずに素直に量産版と呼ぶこともある。

### [Simulator](https://en.wikipedia.org/wiki/Computer_simulation)　(**EDA Methodology/Tool**)
半導体設計においては**回路シミュレーター**を指す。（光学シミュレーターや加工シミュレーター、プロセスシミュレーター等も半導体開発には重要です）

#### [SPICE](https://en.wikipedia.org/wiki/SPICE)
**Simulation Program with Integrated Circuit Emphasis** の略。キルヒホッフの回路方程式を解く回路シミュレーター。1970年代にUC BerkeleyでFORTRAN言語で開発され、SPICE2G6版で実用的に使われるようになった（商用や国内大手が自社開発していたSPICEは、SPICE2G6をルーツにしていた）。商用のSPICEでは、[HSPICE](https://www.synopsys.com/ja-jp/implementation-and-signoff/ams-simulation/primesim-hspice.html)(Synopsys)や[Spector](https://www.cadence.com/ja_JP/home/tools/custom-ic-analog-rf-design/circuit-simulation.html)(Cadence)がデファクト。オープン系ではC言語に書き直されたSPICE3版がベースの[**Ngspice**](https://ngspice.sourceforge.io/)や、並列化に優れた行列ソルバーを導入した[**Xyce**](https://xyce.sandia.gov/)が有名。フリーのSPICEではAnalog Deviceの[LTspice](https://www.analog.com/jp/design-center/design-tools-and-calculators/ltspice-simulator.html)が有名。

#### [Event Driven Simulator](https://en.wikipedia.org/wiki/Discrete-event_simulation)
ロジック回路の動作をトランジスター/ゲート/RTLレベルのプリミティブでトレースするシミュレーター、回路信号の変化＝イベントを時間順にイベントホイールに登録して順番にイベントが信号遅延により伝搬するプリミティブでの新たなイベントの発生を繰り返し登録しながら回路動作を解く。解析精度はイベントホイールの時間刻みとプリミティブ素子や配線の遅延モデルに依存する。VerilogやVHDLのシミュレーターはイベント・ドリブンで実装できる。

#### [Cycle-base Simulator](https://en.wikipedia.org/wiki/Logic_simulation)
ロジック回路の動作を素子の遅延時間を無視して静的に演算順序を決定しておき，実行時にはクロック・サイクルごとに一度だけ演算を行なうことで、イベント・ドリブン手法と比べて、数倍～100倍高速に論理機能検証が可能とする方式。サイクル・ベース・シミュレータでは、実行時の高速化の為にネットリストを一旦コンパイルした後にサイクル毎に演算する。

#### [Fast SPICE](https://www.electronicdesign.com/technologies/test-measurement/article/21801299/whats-the-difference-between-spice-and-fastspice-circuit-simulators)
キルヒホッフの回路方程式を解く回路シミュレーターは、回路規模に伴い回路行列が巨大化するために、シミュレーターの解析スピードが遅くなる課題があった。そこで厳密解を諦めて、回路をある程度の大きさのブロックに切り分けて(Partitioning）行列を小型にすることで高速実行を可能とした回路シミュレーターのこと、回路ブロック間の信号の伝搬はイベント・ドリブンとして扱う等の工夫をしている。90年代頃にEPIC Design Technology社のトランジスターレベルのイベント・ドリブン方式がメモリ設計ツールとして注目されてから開発が加速した。商用ツールとして、**SpectorFX**(Cadence)や**AFS**(Siemens)、**PrimeSim**(Synopsys)等がある。

#### [PSS Simulator](https://en.wikipedia.org/wiki/Periodic_steady-state_analysis)
指定された基本周波数における回路の応答を一周期分計算して周期定常応答を解析する。PSS解析は、回路の周期的な動作点を決定し、周期的な時変小信号解析(位相ノイズ解析）の開始点として利用される。

### [Standard Cell](https://en.wikipedia.org/wiki/Standard_cell)　(**Design Knowledge**)
**SC**とか**スタセル**とか短縮されて呼ばれることが多い。デジタル回路設計用のRTL記述言語([Verilog](https://en.wikipedia.org/wiki/Verilog)や[VHDL](https://en.wikipedia.org/wiki/VHDL))から論理合成ツールを介して最終的にネットとして展開される基本回路（Inverter/NAND/NOR/FF等）群のレイアウトとタイミング(遅延等）情報をまとめたファイル(.lib）を指す。同じ基本回路（例えばInverter)でもネット負荷に応じた駆動能力を持つ複数の素子がライブラリに登録されている。一般にタイミング（遅延）と消費電力はトレードオフの関係にあるので、クリティカルパスを解決するために特別なスタセルを特注・置き換えてタイミングエラーを回避するすることも行われる。また、OAI/AOI等の複合ゲートや、スキャン挿入用のDFF等の特殊回路を登録することも一般的である。

- [Decap Cell](https://ivlsi.com/decap-cells-vlsi-physical-design/)
とは、電源間容量用のスタンダードセルの呼称。電源配線の寄生抵抗に由来する電源電圧のダイナミックな電圧降下を補償する為に、半導体回路を構成するスタンダードセルの近傍に電源間容量（通常はMOS容量素子）を配置する。

- [Filler Cell](https://vlsi.pro/physical-only-cells-filler-cells/)
とは、スタンダードセル間の隙間に挿入してレイアウト上の空き地を埋めることで、電源接続とDRCエラー等の物理的な不都合を解消する為のセル。

- [LEF](https://en.wikipedia.org/wiki/Library_Exchange_Format)
とは、**Library Exchange Format**の略。一般には、P&Rに最低限必要なレイアウト外形とピンの配置だけの設計データを指す。

- [SCAN Cell](https://en.wikipedia.org/wiki/Scan_chain)：
とは、外部から同期回路のラッチ(F/F)の入力信号をシリアルレジスターとして設定可能にできるDFT用のスタンダードセルのこと。「SCANを張る」とは F/F を Scan-F/F に変更して、テスト用の信号を外部から一筆書きになるように配線することを指す。

- [Tap Cell](https://ivlsi.com/tap-cell-placement-vlsi-physical-design/)
とは、チップの基板層（Nwell/Pwell)への電源供給用のセル。適当な間隔で基板へ電源を接続して基板層のインピーダンスを下げて[**ラッチアップ**](https://en.wikipedia.org/wiki/Latch-up)によるチップの破壊を予防する。半導体物理をかじっていないと全く意味不明だが、ひたすらDRCのエラーを消さないと大変なことになる。

## 【X - Z】
