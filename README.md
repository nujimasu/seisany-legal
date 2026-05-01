# Seisany 法務文書（GitHub Pages 公開用）

このディレクトリには、App Store / Google Play の審査で必要となる **公開 URL 版** のプライバシーポリシー・利用規約を格納しています。

## ファイル

| ファイル | 用途 |
|---|---|
| `index.md` | トップページ（両規約へのリンク） |
| `privacy.md` | プライバシーポリシー（日本語 + 英語） |
| `terms.md` | 利用規約（日本語 + 英語） |

## GitHub Pages での公開手順

### 1. 新規リポジトリを作成

GitHub で `seisany-legal` リポジトリを作成（**public**）。

### 2. ファイルを配置してプッシュ

```bash
mkdir ~/seisany-legal && cd ~/seisany-legal
git init
cp /Users/junusami/Documents/Claudeプライベート/seisany/docs/legal/*.md .

git add .
git commit -m "Initial legal pages"
git branch -M main
git remote add origin https://github.com/nujimasu/seisany-legal.git
git push -u origin main
```

### 3. GitHub Pages を有効化

1. リポジトリ → **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main` / `/ (root)`
4. **Save**

数分後、以下の URL で公開される:

- トップ: `https://nujimasu.github.io/seisany-legal/`
- プライバシーポリシー: `https://nujimasu.github.io/seisany-legal/privacy.html`
- 利用規約: `https://nujimasu.github.io/seisany-legal/terms.html`

### 4. ストアに URL を登録

- **App Store Connect**: App Information → Privacy Policy URL → `https://nujimasu.github.io/seisany-legal/privacy.html`
- **Google Play Console**: アプリのコンテンツ → プライバシーポリシー → 同上の URL

## 更新時の運用

規約を変更したら:

1. このディレクトリの該当 `.md` を編集し、「最終更新日」を今日に更新
2. `seisany-legal` リポジトリにコピーしてプッシュ → GitHub Pages が自動反映（通常数分）
3. Seisany アプリ内の `PrivacyPolicyScreen.tsx` / `TermsOfServiceScreen.tsx` にも同じ変更を反映
