# Claude Code DeepResearch Agent

Web検索に特化したClaude Code Sub Agentです。複数の情報源から包括的に情報を収集し、構造化された検索結果を提供します。

## 特徴

- 🔍 **並列検索**: 複数の検索クエリを同時実行して効率的な情報収集
- 🌐 **多言語対応**: 日本語・英語両方での検索戦略
- 📊 **信頼性評価**: 情報源の信頼度を評価し、明記
- 📝 **構造化出力**: 階層的に整理された検索結果
- 🚀 **コンテキスト節約**: Sub Agent機能によりメインのコンテキストを温存

## インストール方法

### 1. プロジェクト単位での導入

```bash
# プロジェクトのルートディレクトリで実行
mkdir -p .claude/agents
curl -o .claude/agents/deepresearch-websearch.md https://raw.githubusercontent.com/MocA-Love/claude-code-deepresearch-agent/refs/heads/main/deepresearch-websearch.md
```

### 2. グローバル導入（全プロジェクトで使用可能）

```bash
# ホームディレクトリで実行
mkdir -p ~/.claude/agents
curl -o ~/.claude/agents/deepresearch-websearch.md https://raw.githubusercontent.com/MocA-Love/claude-code-deepresearch-agent/refs/heads/main/deepresearch-websearch.md
```

### 3. 確認

Claude Codeで以下のコマンドを実行して、エージェントが認識されているか確認：

```
/agents
```

## 使用方法

### 基本的な使い方

```
deepresearch-websearch [検索したい内容]
```

### 使用例

#### 技術調査
```
deepresearch-websearch Claude 4 Sonnetの最新機能について教えてください
```

#### トラブルシューティング
```
deepresearch-websearch TypeScript "Cannot find module" エラーの解決方法
```

#### 比較調査
```
deepresearch-websearch Next.js vs Remix フレームワーク比較 2025年
```

## エージェントの動作フロー

1. **検索計画の立案**
   - ユーザーの質問を分析
   - 3-5個の検索クエリを設計
   - 日本語・英語両方での検索を考慮

2. **並列検索の実行**
   - WebSearchツールで複数クエリを同時実行
   - 公式ドキュメントや信頼できる情報源を優先

3. **詳細情報の取得**
   - WebFetchツールで有望なURLから詳細を取得
   - 必要に応じて追加検索を実施

4. **情報の分析と統合**
   - 収集した情報の信頼性を評価
   - 矛盾する情報の明確な提示
   - 構造化された形式で整理

5. **結果の出力**
   - 要約と詳細情報を階層的に提示
   - 情報源URLと日付を明記
   - 検索メタデータを含む

## 出力形式

エージェントは以下の形式で結果を返します：

```markdown
## 検索結果サマリー

### 要約
[3-5文で核心的な回答]

### 詳細情報
1. 基本概念
2. 実装方法
3. 注意事項

### 参考資料
- [タイトル](URL) - 情報の要約

### 検索メタデータ
- 検索実行日時
- 使用した検索クエリ
- 情報の信頼度
```

## カスタマイズ

エージェントの動作をカスタマイズしたい場合は、`deepresearch-websearch.md`を編集してください：

- 検索戦略の調整
- 出力形式の変更
- 優先する情報源の指定
- 言語設定の変更

## メリット

### コンテキスト枯渇問題の解決
通常のClaude Codeセッションでは、大量の検索や情報収集を行うとコンテキストウィンドウが枯渇しがちです。このSub Agentを使用することで：

- メインセッションのコンテキストを温存
- 検索タスクを独立したコンテキストで実行
- 必要な情報のみをメインセッションに返す

### 検索品質の向上
専門化されたプロンプトとワークフローにより：

- より適切な検索クエリの生成
- 情報の信頼性評価
- 構造化された結果の提供

## トラブルシューティング

### エージェントが見つからない場合
```bash
# 設定ディレクトリの確認
ls -la ~/.claude/agents/
ls -la .claude/agents/
```

### 検索が遅い場合
- 検索クエリの数を減らす
- 特定のドメインに限定した検索を試す

## 貢献

改善案やバグ報告は、GitHubのIssuesまたはPull Requestでお願いします。

## ライセンス

MIT License
