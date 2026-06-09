# モデル予測制御 (MPC) インタラクティブ教材（制御理論教科書 併用版）

[![Live Demo](https://img.shields.io/badge/%E2%96%B6_Live_Demo-GitHub_Pages-2563eb)](https://lutelute.github.io/lec-mpc/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-4caf50)](LICENSE)
[![Dependencies](https://img.shields.io/badge/dependencies-none-success)](#技術メモ)
[![Math: MathML](https://img.shields.io/badge/math-MathML-ff9800)](#技術メモ)
[![Single-file HTML](https://img.shields.io/badge/single--file-HTML%2FCSS%2FJS-607d8b)](#フォルダ構成)

> ### 🌐 公開教材（ブラウザですぐ動く）→ **<https://lutelute.github.io/lec-mpc/>**
> 学生にはこのトップ URL を渡すだけで OK です。

制御工学の教科書で **PID 制御・状態空間・最適制御 (LQR)** までを学んだ学習者を対象に、
モデル予測制御を **予測 → 最適化 → 受け取り (receding horizon)** の流れで体験し、さらに
**制約の扱い・実用例・最新動向** までを一望できる教材スイートです。
すべてブラウザだけで動き、外部ライブラリ・ネット接続は不要です。

---

## ✨ 特徴

- 🎮 **触って学ぶデモ** — 予測軌道・最適入力列・receding horizon をスライダーとボタンで体験。制約付き MPC は QP をブラウザ内で実時間求解
- 📐 **数式は MathML・図は SVG** — 単一 HTML で完結、ライブラリ・CDN 不要
- 🌗 **ライト/ダークモード自動対応** — OS 設定に追従
- 📐 **制御の各方面からアクセス** — ブロック線図・**MPC vs PID 並走比較**・**閉ループ極 (z 平面) で安定性**・ステップ応答指標（行き過ぎ量/整定時間）・外乱応答を、4 プラント（1次系・台車・振動系・倒立振子）切替で 1 画面に
- 📚 **古典・現代制御 (PID/LQR) と接続** — 「無制約 MPC ＝ 状態フィードバック」を講義ノート＋演習7問＋例題集（模範解答つき・数値検証済み）で
- 🏭 **実用例・最新動向** — 石油化学プロセスから自動運転・ロケット着陸・組込み高速ソルバまで、出典つき
- 🍎 **配布が簡単** — ダブルクリックで開くだけ／フォルダごとコピー可

---

## 教材を開く（クリックで動きます）

### 中核（学習順）

| # | 教材 | 役割 |
|---|---|---|
| 🏠 | **[教材トップ（ポータル）](https://lutelute.github.io/lec-mpc/)** | 学習フロー・教科書対応表・全導線 |
| 1 | **[Step 1：受け取りホライズン デモ ▶](https://lutelute.github.io/lec-mpc/demos/mpc_receding_horizon.html)** | 無制約 MPC。予測・最適化・先頭だけ適用して再計算 |
| 2 | **[Step 2：制約付き MPC デモ ▶](https://lutelute.github.io/lec-mpc/demos/mpc_constrained.html)** | 入力飽和・出力天井を QP（Hildreth 法）で処理 |
| 3 | **[Step 3：MPC を制御として見る ▶](https://lutelute.github.io/lec-mpc/demos/mpc_vs_pid.html)** | ブロック線図・MPC vs PID 並走・閉ループ極(z平面)・ステップ応答指標を 4 プラントで比較 |
| 4 | **[Step 4：講義ノート ▶](https://lutelute.github.io/lec-mpc/content/lecture-notes.html)** | 予測方程式・二次コスト・受け取り原理・制約と QP・安定性・演習7問 |
| 5 | **[Step 5：例題集 ▶](https://lutelute.github.io/lec-mpc/content/worked-examples.html)** | 予測行列・安定性・MPC vs PID の数値例（解つき・検証済み） |
| 発展 | **[応用ショーケース ▶](https://lutelute.github.io/lec-mpc/content/mpc-applications.html)** | 歴史・実用例・最新動向＋ミニデモ |

### 補助資料

| 教材 | 役割 | 対象 |
|---|---|---|
| **[デモ操作ガイド ▶](https://lutelute.github.io/lec-mpc/guides/how-to-use.html)** | 各 UI の見方・観察ポイント | 学生 |
| **[教員用ガイド＋模範解答 ▶](https://lutelute.github.io/lec-mpc/guides/teacher-guide.html)** | 授業展開・時間配分・解答・ルーブリック | 教員 |
| **[配布用サマリー1枚 ▶](https://lutelute.github.io/lec-mpc/guides/overview.html)** | 教材全体マップ（印刷対応） | 配布用 |

> ⚠ `teacher-guide.html` は演習の**模範解答**を含みます。公開しているため URL 直打ちで閲覧可能です。学生にはトップ URL のみ案内してください。

---

## フォルダ構成

```
lec-mpc/
├── index.html                … 教材トップ（ポータル）
├── README.md
├── LICENSE                   … CC BY 4.0
├── CITATION.cff              … 引用情報（GitHub "Cite this repository"）
├── demos/                    … 触って動かす体験デモ
│   ├── mpc_receding_horizon.html   … Step 1（無制約・受け取り）
│   ├── mpc_constrained.html        … Step 2（制約付き・QP）
│   └── mpc_vs_pid.html             … Step 3（制御として見る・MPC vs PID・z平面・安定性）
├── content/                  … 学習コンテンツ
│   ├── lecture-notes.html          … Step 4（理論・演習・安定性）
│   ├── worked-examples.html        … 例題集（数値例・解つき）
│   └── mpc-applications.html       … 発展（応用ショーケース）
└── guides/                   … ガイド・補助資料
    ├── how-to-use.html             … デモ操作ガイド
    ├── teacher-guide.html          … 教員ガイド＋解答
    └── overview.html               … 配布サマリー（印刷用）
```

> 相互リンクはすべて相対パス。フォルダごと移動・コピーしても動作します。ローカルでは `index.html` をダブルクリックで開けます（インストール・ネット接続不要）。

---

## 使い方

### 学生
1. [教材トップ](https://lutelute.github.io/lec-mpc/) を開く。
2. **Step 1 → Step 2 → 講義ノート → 応用ショーケース** の順に進む。操作に迷ったら [デモ操作ガイド](https://lutelute.github.io/lec-mpc/guides/how-to-use.html)。
3. 講義ノート §7 の演習を「手計算 → デモで答え合わせ」の順で解く。

### 教員
- [教員用ガイド](https://lutelute.github.io/lec-mpc/guides/teacher-guide.html) に授業展開（2〜3 コマ）・時間配分・**演習7問の完全解答（数値検証済み）**・評価ルーブリックを収録。
- スライダーで「予測ホライズン・重み・制約を変えると応答がどう変わるか」をリアルタイムに提示できます。
- [配布用サマリー](https://lutelute.github.io/lec-mpc/guides/overview.html) を `⌘/Ctrl + P` で PDF 化すれば配布プリントになります。

---

## 制御理論の教科書との接続（要点）

この教材の主眼は、MPC を**古典・現代制御の延長線上**に位置づけることです。

- 二次コスト `J = Σ‖ŷ−r‖²_Q + Σ‖u‖²_R` を最小化する点は **LQR と同じ**。違いは「有限ホライズン・制約あり・オンライン」。
- **制約が無ければ、無制約 MPC は状態フィードバック `u = −K·x` に一致**する（先頭行ゲイン、`Np→∞` で LQR）。
- **入力飽和の最適処理**は、PID のアンチワインドアップを一般化したものとして読める。
- 予測ホライズン `Np`・制御ホライズン `Nc`・重み `λ=R/Q` の調整 ＝ 古典制御の**ゲインチューニング**に対応。

→ 対応表は[教材トップ](https://lutelute.github.io/lec-mpc/)、導出は[講義ノート §6](https://lutelute.github.io/lec-mpc/content/lecture-notes.html#s6)、定量的な解答は[教員ガイド](https://lutelute.github.io/lec-mpc/guides/teacher-guide.html)を参照。
特定の教科書に依存しないよう、古典制御（PID）・現代制御（状態空間・LQR）の標準的内容に対応づけています。

---

## 応用・最新動向（[応用ショーケース](https://lutelute.github.io/lec-mpc/content/mpc-applications.html)）

- **歴史**：Richalet ら IDCOM/MPHC(1978) → Cutler & Ramaker DMC(1980, Shell) → García–Prett–Morari サーベイ(1989) → Clarke ら GPC(1987) → Mayne ら 安定性理論(2000) → Bemporad ら 明示的 MPC(2002) → 組込み高速 QP ソルバと NMPC の時代
- **実用例**：石油化学・製油所のプロセス制御（MPC 発祥の地）、自動車（エンジン・ACC・自動運転の軌道生成）、航空宇宙（ロケット着陸の凸最適化誘導）、電力・ビル空調 (HVAC)、ロボット（脚式・ドローン）
- **手法の系譜**：DMC / GPC / 線形 MPC / 非線形 MPC (NMPC) / 明示的 MPC / ロバスト MPC / 確率 MPC / 経済 MPC (EMPC)
- **最新動向**：学習ベース MPC、MPC + 強化学習、微分可能 MPC、リアルタイム反復、組込みソルバ（OSQP・qpOASES・acados）

> 年代・「世界初」系の主張は範囲限定が必要なため、ページ内に**正確性メモ**を併記し、主要な一次文献の出典を明示しています（研究引用時は一次文献の確認を推奨）。

---

## 推奨カリキュラム配置

- 現代制御（状態空間・LQR）を一通り終えた後の **発展トピック**として 2〜3 コマ。
- 所要の目安：デモ体験 40 分＋講義ノート 60〜90 分（＋応用ショーケース 15〜20 分）。

---

## 技術メモ

- 各 HTML は**単一ファイル完結**（HTML/CSS/JavaScript インライン、外部依存なし）。
- 数式は **MathML**（モダンブラウザがネイティブ表示）。グラフ・図は **SVG** を JavaScript で描画。
- ライト／ダークモードに自動対応（OS 設定に追従）。
- 予測：離散時間状態空間モデル（2 重積分系）。無制約 MPC は最小二乗の解析解、制約付き MPC は **二次計画 (QP) を Hildreth 双対法**でブラウザ内求解。
- 演習の解答値・収束挙動・QP の制約充足は、別途 Node.js で数値検証済み（逆行列誤差 ~1e-16、各設定で目標収束・制約満足を確認）。

---

## 📄 ライセンス

本教材は **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE)** で公開しています。
クレジットを表示すれば、**改変・再配布・商用利用も自由**です。授業・自習でご自由にお使いください。

> 応用ショーケースが引用する実在の製品・年代・研究は、各出典元に帰属します（教育目的での引用）。

## 引用 / Citation

利用・引用の際は以下をご記載ください（GitHub の **"Cite this repository"** ボタンからも取得できます）。

> lutelute (PWS Lab). *モデル予測制御 (MPC) インタラクティブ教材（制御理論教科書 併用版）*. 2026.
> https://github.com/lutelute/lec-mpc
