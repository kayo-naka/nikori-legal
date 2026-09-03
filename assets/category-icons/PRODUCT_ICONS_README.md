# 商品カテゴリの絵 13枚（2026-09-03・利用者が Figma から書き出したもの）

## 出どころ
利用者が `nikori/img/` に置いた 13枚（[D-189]「下記figmaからとってきて」への回答）。
同じフォルダの LP スクショ（`スクリーンショット 2026-09-03 9.01.42.png`）と突き合わせて割り当てた。

## 元のファイル名 → ここでの名前
| 元 | ここ | 使うカテゴリ |
|---|---|---|
| `face 1.svg` | `cosme.svg` | コスメ |
| `face 1-1.svg` | `bottle_pump.svg` | シャンプー ／ リンス |
| `Group 18.svg` | `tube.svg` | 洗顔 ／ クレンジング ／ 日焼け止め |
| `Group 20.svg` | `bottle_cylinder.svg` | 化粧水 ／ 美容液 ／ 乳液 |
| `face 1-2.svg` | `sheet_mask.svg` | パック |
| `face 1-3.svg` | `jar.svg` | ボディクリーム ／ 入浴剤 ／ スクラブ |
| `face 1-4.svg` | `hair_dryer.svg` | ドライヤー |
| `xsx.svg` | `hair_iron.svg` | ヘアアイロン ／ 美髪器具 |
| `sdb.svg` | `curl_iron.svg` | カールアイロン |
| `dsgs.svg` | `humidifier.svg` | 加湿器 |
| `dsdg.svg` | `facial_device.svg` | 美顔器 |
| `gfdface 1-4.svg` | `led_mask.svg` | LEDマスク |
| `face 1-5.svg` | `shapes_other.svg` | その他 |

🔴 **絵が無い 2件** ＝ 脱毛器（かばん型）／運動器具（人が伸びをする形）。
　　利用者の判断待ち。それまでは Material Symbols のままにする。

## 直したこと（🔬 全部 実測つき）
1. 🔴 **大きさ** ── `Group 18` と `Group 20` だけ viewBox が他と違い、
   `.cat-ico svg{width:85px;height:85px}` の枠で ink が 85.0px（＝枠いっぱい）になっていた。
   設計（LPスクショ実測）は 66.9 / 71.7 相当。⇒ `0 0 86 96` に置き直して **13枚とも ±1.1px** に。
   ```
   🔬 直す前 tube 85.0 ／ bottle_cylinder 85.0
   🎯 直した後 tube 67 ／ bottle_cylinder 71   （設計 66.9 / 71.7）
   🔵 他の11枚は元から設計どおり（差 ≤0.7px）＝触っていない
   ```
2. 🔴 **色** ── 13枚とも色を直書きしていた。うち 2枚が `#FF801E`
   （🔴 `--orange` は `#FF801F`。1桁違う）。⇒ 全部 `currentColor` へ。
   ```
   🔬 直す前 色の直書き 19件 ／ 🎯 直した後 0件
   🔵 既存32枚のうち 27枚が currentColor＝これに合わせた
   ```
3. `<svg>` の `width` / `height` を外した（CSS の 85px が効くように）。
   🔵 中の `<rect width=...>` は形の一部なので残している。

## 🔴 まだやっていないこと
`index.html` への配線。割り当ての確認が済んでから。
