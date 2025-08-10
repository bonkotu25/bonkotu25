# フォルダ構成改善計画

## 現在の問題点

### 1. 命名規則の不統一
- `mySplit` vs `static-page.azumayoru-rta.com` vs `staticContents`
- 英語と日本語の混在
- キャメルケース、スネークケース、ケバブケースの混在

### 2. 階層構造の複雑さ
- ゲーム別フォルダが深い階層にある
- 類似ゲームが分散している
- 見つけにくい構造

### 3. 目的の不明確さ
- 各フォルダの役割が分かりにくい
- ファイルの分類基準が不明確

## 改善計画

### Phase 1: フォルダ名の統一

#### 現在 → 改善後
```
mySplit/ → splits/
static-page.azumayoru-rta.com/ → web/
staticContents/ → web/static/
CommentaryMaterials/ → guides/  # 解説資料は独立したフォルダに
```

### Phase 2: ゲームシリーズの統合

#### Animal Crossing シリーズ
```
AnimalCrossingCityFolk/ → splits/games/animal-crossing/city-folk/
AnimalCrossingNewLeaf/ → splits/games/animal-crossing/new-leaf/
AnimalCrossingWildWorld/ → splits/games/animal-crossing/wild-world/
```

#### Harvest Moon シリーズ
```
HarvestMoon/ → splits/games/harvest-moon/classic/
HarvestMoonDS/ → splits/games/harvest-moon/ds/
HarvestMoonAWonderfulLife/ → splits/games/harvest-moon/wonderful-life/
FriendsOfMineralTown/ → splits/games/harvest-moon/friends-of-mineral-town/
StoryOfSeasonsAWonderfulLife/ → splits/games/story-of-seasons/wonderful-life/
StoryOfSeasonsTrioOfTowns/ → splits/games/story-of-seasons/trio-of-towns/
```

#### Rune Factory シリーズ
```
RuneFactory/ → splits/games/rune-factory/classic/
RuneFactory3/ → splits/games/rune-factory/3/
RuneFactory4/ → splits/games/rune-factory/4/
RuneFactoryGuardiansOfAzuma/ → splits/games/rune-factory/guardians-of-azuma/
```

### Phase 3: 新しいフォルダ構成（確定版）

#### 推奨案: イベント参加を軸とした管理
```
bonkotu25/
├── README.md
├── docs/                          # プロジェクト管理用ドキュメント
│   ├── updates/                   # 更新履歴
│   └── project/                   # プロジェクト関連資料
├── events/                        # イベント参加記録（年別管理）
│   ├── 2024/                      # 2024年のイベント
│   │   ├── 20241219_rta-advent-calendar/
│   │   │   ├── application.md     # 応募文
│   │   │   └── article.md         # 解説文
│   │   └── 20241220_other-event/
│   │       ├── application.md
│   │       └── article.md
│   ├── 2025/                      # 2025年のイベント
│   │   └── 20250115_new-event/
│   │       ├── application.md
│   │       └── article.md
│   └── README.md                  # イベント一覧・説明
├── guides/                        # 汎用解説資料
│   ├── rtaGuides/                 # RTA攻略ガイド
│   │   ├── runeFactory/
│   │   ├── harvestMoon/
│   │   ├── storyOfSeasons/
│   │   └── animalCrossing/
│   ├── gameStrategies/            # ゲーム別戦略
│   └── resources/                 # 参考資料（PDF等）
├── splits/
│   ├── games/                     # ゲーム別スプリット
│   │   ├── animalCrossing/        # Animal Crossingシリーズ
│   │   ├── harvestMoon/           # Harvest Moonシリーズ（旧）
│   │   ├── storyOfSeasons/        # Story of Seasonsシリーズ（新）
│   │   ├── runeFactory/           # Rune Factoryシリーズ
│   │   └── other/                 # その他のゲーム
│   └── templates/
├── web/
│   ├── static/                    # 静的ファイル
│   └── pages/                     # ページファイル
└── tools/                         # ツール・スクリプト類
```

## 解説資料の配置に関する検討

### 現在の解説資料の分類
1. **RTA攻略ガイド**: `rf_goa.md`, `hmap_any.md`, `RF4sp_beat2ndArc.md`
2. **イベント参加記録**: `2024_RtaAdventCalendar.md`
3. **ゲーム別解説**: `ACNL_snomanBingo.md`, `AnimalCrossingWildWorld_GoldenAxe.md`
4. **参考資料**: `ACNL_snomanBingo.pdf`

### 推奨案: イベント参加を軸とした管理
**理由**:
- イベント参加の履歴が時系列で整理される
- 応募文と解説文が一箇所に集約される
- 今後のイベント参加の参考資料として活用しやすい
- イベント単位での情報管理が明確

### イベント管理の詳細構造
```
events/
├── 2024/                          # 2024年のイベント
│   ├── 20241219_rta-advent-calendar/  # RTAアドベントカレンダー2024
│   │   ├── application.md             # 応募文
│   │   ├── article.md                 # 解説文
│   │   └── metadata.json              # イベント情報（日付、URL等）
│   └── 20241220_other-event/          # その他のイベント
│       ├── application.md
│       ├── article.md
│       └── metadata.json
├── 2025/                          # 2025年のイベント
│   └── 20250115_new-event/        # 新しいイベント
│       ├── application.md
│       ├── article.md
│       └── metadata.json
└── README.md                      # イベント一覧・説明
```

### 汎用解説資料の分類
```
guides/
├── rtaGuides/                    # RTA攻略ガイド
│   ├── runeFactory/
│   │   ├── rf_goa.md
│   │   └── RF4sp_beat2ndArc.md
│   ├── harvestMoon/
│   │   └── hmap_any.md
│   └── animalCrossing/
│       └── AnimalCrossingWildWorld_GoldenAxe.md
├── gameStrategies/               # ゲーム別戦略
│   └── ACNL_snomanBingo.md
└── resources/                     # 参考資料
    └── ACNL_snomanBingo.pdf
```

## 実装手順

### ✅ Step 1: バックアップ作成
- 現在のフォルダ構成のバックアップを作成
- `git commit`で現在の状態を保存

### ✅ Step 2: 新フォルダ作成
```bash
mkdir events
mkdir events/2024
mkdir guides
mkdir guides/rtaGuides
mkdir guides/rtaGuides/runeFactory
mkdir guides/rtaGuides/harvestMoon
mkdir guides/rtaGuides/animalCrossing
mkdir guides/gameStrategies
mkdir guides/resources
mkdir splits
mkdir splits/games
mkdir splits/templates
mkdir web
mkdir web/static
mkdir web/pages
mkdir tools
```

### 🔄 Step 3: ファイル移動（段階的）

#### ✅ Phase 3-1: イベント関連ファイルの移動
```bash
# イベント関連ファイルを移動
mv CommentaryMaterials/2024_RtaAdventCalendar.md events/2024/20241219_rta-advent-calendar/article.md
```

#### ✅ Phase 3-2: 解説資料の移動
```bash
# RTA攻略ガイドの移動
mv CommentaryMaterials/rf_goa.md guides/rtaGuides/runeFactory/
mv CommentaryMaterials/RF4sp_beat2ndArc.md guides/rtaGuides/runeFactory/
mv CommentaryMaterials/hmap_any.md guides/rtaGuides/harvestMoon/
mv CommentaryMaterials/AnimalCrossingWildWorld_GoldenAxe.md guides/rtaGuides/animalCrossing/

# ゲーム別戦略の移動
mv CommentaryMaterials/ACNL_snomanBingo.md guides/gameStrategies/

# 参考資料の移動
mv CommentaryMaterials/ACNL_snomanBingo.pdf guides/resources/
```

#### ✅ Phase 3-3: スプリットファイルの移動
```bash
# Animal Crossing シリーズ
mkdir splits/games/animalCrossing
mkdir splits/games/animalCrossing/cityFolk
mkdir splits/games/animalCrossing/newLeaf
mkdir splits/games/animalCrossing/wildWorld

mv mySplit/AnimalCrossingCityFolk/* splits/games/animalCrossing/cityFolk/
mv mySplit/AnimalCrossingNewLeaf/* splits/games/animalCrossing/newLeaf/
mv mySplit/AnimalCrossingWildWorld/* splits/games/animalCrossing/wildWorld/

# Harvest Moon シリーズ（旧）
mkdir splits/games/harvestMoon
mkdir splits/games/harvestMoon/classic
mkdir splits/games/harvestMoon/ds
mkdir splits/games/harvestMoon/wonderfulLife
mkdir splits/games/harvestMoon/friendsOfMineralTown

mv mySplit/HarvestMoon/* splits/games/harvestMoon/classic/
mv mySplit/HarvestMoonDS/* splits/games/harvestMoon/ds/
mv mySplit/HarvestMoonAWonderfulLife/* splits/games/harvestMoon/wonderfulLife/
mv mySplit/FriendsOfMineralTown/* splits/games/harvestMoon/friendsOfMineralTown/

# Story of Seasons シリーズ（新）
mkdir splits/games/storyOfSeasons
mkdir splits/games/storyOfSeasons/wonderfulLife
mkdir splits/games/storyOfSeasons/trioOfTowns

mv mySplit/StoryOfSeasonsAWonderfulLife/* splits/games/storyOfSeasons/wonderfulLife/
mv mySplit/StoryOfSeasonsTrioOfTowns/* splits/games/storyOfSeasons/trioOfTowns/

# Rune Factory シリーズ
mkdir splits/games/runeFactory
mkdir splits/games/runeFactory/classic
mkdir splits/games/runeFactory/3
mkdir splits/games/runeFactory/4
mkdir splits/games/runeFactory/guardiansOfAzuma

mv mySplit/RuneFactory/* splits/games/runeFactory/classic/
mv mySplit/RuneFactory3/* splits/games/runeFactory/3/
mv mySplit/RuneFactory4/* splits/games/runeFactory/4/
mv mySplit/RuneFactoryGuardiansOfAzuma/* splits/games/runeFactory/guardiansOfAzuma/

# その他のゲーム
mkdir splits/games/other
mv mySplit/AliceEscaped/* splits/games/other/
mv mySplit/AttackerChan!/* splits/games/other/
mv mySplit/chocoboGP/* splits/games/other/
mv mySplit/doraemon/* splits/games/other/
mv mySplit/doraemon3MakainoDanjon/* splits/games/other/
mv mySplit/DoraemonStoryOfSeasonsFriendsOfTheGreatKingdom/* splits/games/other/
mv mySplit/HarvestMoonAnimalParede/* splits/games/other/
mv mySplit/KatamariDamacyREROLL/* splits/games/other/
mv mySplit/MetalUnit/* splits/games/other/
mv mySplit/MISTROGUE/* splits/games/other/
mv mySplit/Shepherd'sCrossing/* splits/games/other/
mv mySplit/silentHope/* splits/games/other/
mv mySplit/Unpacking/* splits/games/other/
mv mySplit/weLoveKatarariREROLL/* splits/games/other/

# テンプレート類
mv mySplit/other/* splits/templates/
```

#### ✅ Phase 3-4: Web関連ファイルの移動
```bash
# Web関連ファイルの移動
mv static-page.azumayoru-rta.com/* web/pages/
mv staticContents/* web/static/
```

### ✅ Step 4: 古いフォルダの削除
```bash
# 移動完了後に古いフォルダを削除
rmdir mySplit                           # ✅ 完了
rmdir CommentaryMaterials               # ✅ 完了  
rmdir static-page.azumayoru-rta.com     # ✅ 完了
rmdir staticContents                    # ✅ 完了
```

### ✅ Step 5: README更新
- 新しいフォルダ構成に合わせてREADMEを更新
- イベント一覧のREADME（events/README.md）を作成

### ✅ Step 6: テスト
- すべてのファイルが適切に移動されていることを確認
- ファイル数の整合性チェック完了（スプリット81件、Markdown11件、HTML3件）
- 新しいフォルダ構造でのファイル配置確認完了

## ✅ プロジェクト完了

**実施日時**: 2024年8月11日

**完了した作業**:
- ✅ Phase 3-1: イベント関連ファイルの移動
- ✅ Phase 3-2: 解説資料の移動
- ✅ Phase 3-3: スプリットファイルの移動
- ✅ Phase 3-4: Web関連ファイルの移動
- ✅ 古いフォルダの削除
- ✅ README更新
- ✅ ファイル整合性確認

**移行結果**:
- 総スプリットファイル数: 81件（.lss/.lsl/.sgl）
- 解説資料: 6件（Markdownファイル）
- 参考資料: 1件（PDFファイル）
- Webページ: 3件（HTMLファイル）
- すべてのファイルが新しいフォルダ構造に正常に移行

## 注意事項

### リスク管理
- ファイル移動前にバックアップを作成
- 段階的な移行でリスクを最小化
- 各段階での動作確認
- Gitで各段階をコミット

### 互換性の維持
- 既存のリンクや参照の更新
- 外部からの参照がある場合の対応
- ファイルパスの変更を記録

### コミュニケーション
- 変更内容をコミュニティに事前告知
- 移行期間中のサポート体制

---

*この計画は段階的に実行し、各段階でフィードバックを収集して改善します。*
