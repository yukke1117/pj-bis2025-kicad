# af-pj-bis2025

精密アナログ信号処理・データ取得回路のKiCadプロジェクト

## 概要

本プロジェクトは、高精度アナログ信号の取得・調整を目的とした回路基板設計です。24ビットADCを中心に、低ノイズ電源回路とオペアンプによる信号調整回路を組み合わせています。STM32マイコンとの接続を想定した拡張基板として設計されています。

## 主要スペック

- **ADC**: ADS1220IPW (24-bit, TI)
- **オペアンプ**: OPA2380AIDGKR (デュアル), THS4552IPWR (全差動)
- **電圧リファレンス**: REF5050IDR (5V), ADR130BUJZ-REEL7 (精密)
- **電源IC**: MIC5237-5.0YT (5V LDO), UA78L06ACPK (6Vリニアレギュレータ)
- **MOSFET**: ALD114904APAL (低閾値)
- **精密アンプ**: LT1991ACMS-TRPBF
- **コネクタ**: FH28-10S-0.5SH (FPC), SMAコネクタ x2, CN7/CN10 (STM32 Nucleo互換)

## ディレクトリ構成

```
pj-bis2025-kicad/
├── af-pj-bis2025.kicad_pro      # プロジェクトファイル
├── af-pj-bis2025.kicad_sch      # 回路図
├── af-pj-bis2025.kicad_pcb      # PCBレイアウト
├── af-pj-bis2025.kicad_prl      # プロジェクトローカル設定
├── af-pj-bis2025.csv            # 部品表 (BOM)
├── af-pj-bis2025.glb            # 3Dモデル (GLB形式)
├── freerouting.dsn              # 自動配線用ファイル
├── af-pj-bis2025-backups/       # バックアップファイル
├── pj-bis2025.pretty/           # カスタムフットプリントライブラリ
├── pj-bis2025.kicad_sym         # カスタムシンボルライブラリ
├── ultralibrary_zip/            # コンポーネントライブラリ (Ultra Librarian)
├── step/                        # 3Dモデルファイル (STEP形式)
├── stm32/                       # STM32関連サブプロジェクト
│   ├── stm32.kicad_sch          # STM32回路図
│   └── stm32.kicad_pcb          # STM32 PCBレイアウト
├── production/                  # JLCPCB製造用ファイル
│   ├── af-pj-bis2025.zip        # ガーバーファイル一式
│   ├── bom.csv                  # 部品表
│   ├── positions.csv            # 実装位置データ
│   └── netlist.ipc              # IPCネットリスト
└── jlcpcb/                      # JLCPCB製造設定
```

## カスタムライブラリ

### pj-bis2025.pretty (フットプリント)

| フットプリント | 説明 |
|--------------|------|
| ADS1220-PW16-M | ADC (TSSOP-16) |
| OPA2380-DGK8-M | デュアルオペアンプ (VSSOP-8) |
| THS4552-PW0016A_M | 全差動アンプ (TSSOP-16) |
| REF5050-D8-M | 電圧リファレンス (SOIC-8) |
| LT1991-MSOP-10_MS_LIT-M | 精密アンプ (MSOP-10) |
| MIC5237_5_0YT | 5V LDO (SOT-223) |
| UA78L06ACPK-PK0003A_M | 6Vレギュレータ (SOT-89) |
| ADR130BUJZ_REEL7 | 精密電圧リファレンス (SOT-23) |
| ALD114904APAL-8-PDIP_ALD | MOSFET (PDIP-8) |
| HIROSE_FH28-10S-0.5SH_05_ | FPCコネクタ |
| PTS_647_SN50_SMTR2_LFS | プッシュボタンスイッチ |

### ultralibrary_zip (Ultra Librarian)

Ultra Librarianからダウンロードしたコンポーネントライブラリを含みます。

## 必要環境

- **KiCad 9.0** 以上

## 設計ルール

| 項目 | 値 |
|------|-----|
| 最小トラック幅 | 0.25mm |
| 最小クリアランス | 0.2mm |
| ビア径 | 0.6mm |
| ビアドリル | 0.3mm |
| 最小ホールクリアランス | 0.28mm |
| エッジクリアランス | 0.5mm |

## 製造

製造ファイルは `production/` ディレクトリに出力済みです。JLCPCB向けの以下のファイルが含まれています:

- `af-pj-bis2025.zip` - ガーバーファイル一式
- `bom.csv` - 部品表 (SMT実装用)
- `positions.csv` - 部品配置データ (SMT実装用)

## ライセンス

senserity

## 更新履歴

- 2025-01-23: 基板完成、DRCエラーフリー
- 2025-01-20: GNDベタ配置、アナログ配線完了
- 2025-01-19: アノテーション再定義、フットプリント更新
- 2025-01-18: PCBレイアウト変更
- 2024-11-24: 初期設計
