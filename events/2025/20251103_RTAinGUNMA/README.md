# イベント参加用テンプレート

このフォルダには、新しいイベントに参加する際に使用するテンプレートファイルが含まれています。

## 📋 テンプレートファイル

### 1. `application-template.md`
イベント応募時に使用するテンプレート

### 2. `article-template.md`
解説記事執筆時に使用するテンプレート

### 3. `metadata-template.json`
イベント情報管理用のメタデータテンプレート

## 🚀 使用方法

### 新しいイベント参加時の手順

1. **フォルダ作成**
   ```bash
   mkdir events/[年]/[YYYYMMDD_イベント名]
   cd events/[年]/[YYYYMMDD_イベント名]
   ```

2. **テンプレートファイルをコピー**
   ```bash
   cp ../templates/application-template.md application.md
   cp ../templates/article-template.md article.md
   cp ../templates/metadata-template.json metadata.json
   ```

3. **各ファイルを編集**
   - `application.md`: 応募内容を記入
   - `article.md`: 解説記事を執筆
   - `metadata.json`: イベント情報を更新

### フォルダ命名規則
```
events/[年]/[YYYYMMDD_イベント名]/
```

**例**:
- `events/2025/20250315_rta-advent-calendar/`
- `events/2025/20250701_summer-rta-festival/`

## 📝 カスタマイズのヒント

### application.md
- イベントの特性に応じて応募項目を調整
- 過去の応募例を参考に内容を充実

### article.md
- ゲームジャンルに応じて構成をカスタマイズ
- 図表や動画リンクの追加を検討

### metadata.json
- タグは検索性を考慮して適切に設定
- ファイル管理のために詳細情報を記録

---

*テンプレートは随時改良していきます。新しいイベント形式に応じて更新してください。*