# af-pj-bis2025

精密アナログ信号処理・データ取得回路のKiCadプロジェクト

## 概要

本プロジェクトは、高精度アナログ信号の取得・調整を目的とした回路基板設計です。24ビットADCを中心に、低ノイズ電源回路とオペアンプによる信号調整回路を組み合わせています。

## 主要スペック

- **ADC**: ADS127L14IRSHT (24-bit, TI)
- **オペアンプ**: OPA380AID, OPA210IDBVR, THS4552IPWR
- **電圧リファレンス**: REF6225IDGKR
- **電源IC**: MIC5237-5.0YU (5V LDO), TPS7A4700RGWR (低ノイズLDO)
- **電源レール**: +9V, +6V, +2.5V, GND

## ディレクトリ構成

```
pj-bis2025-kicad/
├── af-pj-bis2025.kicad_pro      # プロジェクトファイル
├── af-pj-bis2025.kicad_sch      # 回路図
├── af-pj-bis2025.kicad_pcb      # PCBレイアウト
├── af-pj-bis2025.kicad_prl      # プロジェクトレイアウトルール
├── af-pj-bis2025-backups/       # バックアップファイル
├── ultralibrary_zip/            # カスタムコンポーネントライブラリ
├── jlcpcb/                      # 製造用ファイル
│   ├── gerber/                  # ガーバーファイル
│   └── production_files/        # 製造ドキュメント
└── step/                        # 3Dモデルファイル
```

## カスタムライブラリ

`ultralibrary_zip/` ディレクトリに以下のコンポーネントライブラリを含みます:

### アナログIC
- ADS1220IPW - マルチチャネルADC
- OPA2380AIDGKR - デュアルオペアンプ
- LT1991ACMS-TRPBF - 精密アンプ
- THS4552IPWR - オペアンプ
- REF5050IDR - 電圧リファレンス

### 電源IC
- MIC5237 - 5V LDOレギュレータ
- UA78L06ACPK - 6Vリニアレギュレータ

### 受動部品
- 各種タンタルコンデンサ（LDO出力用、Vref用）
- PTS_647_SN50_SMTR2_LFS - プッシュボタンスイッチ

## 必要環境

- **KiCad 9.0** 以上

## 設計ルール

| 項目 | 値 |
|------|-----|
| 最小トラック幅 | 0.2mm |
| 最小クリアランス | 0.2mm |
| ビア径 | 0.6mm |
| ビアドリル | 0.3mm |

## ライセンス

senserity

## 更新履歴

- 2025-11-24: 初期設計
