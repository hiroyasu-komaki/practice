# practice(update 2024-07-15)

## Git/Githubの基本的な使い方

### 新しいブランチを作成してから、ブランチをプッシュするまで

```
# 現在のブランチを確認
git branch

# リモートリポジトリの最新の変更を取得
git fetch origin

# 新しいブランチを作成し、切り替え
git checkout -b feature-branch origin/main
git branch --set-upstream-to=origin/feature-branch

# 必要な作業を行う
# (例: ファイルの追加や修正)

# 変更をステージングしてコミット
git add .
git commit -m "Add new feature"

# 新しいブランチをリモートリポジトリにプッシュ
git push origin feature-branch

```

### 作業完了後、mainブランチの変更を取り込んでから、ブッシュするまで

```
# リモートブランチの変更を取り込み
git fetch origin

git checkout feature-branch

# コンフリクトが発生した場合、解決して続行

# コミット履歴を統合する場合
git rebase origin/main

# コミット履歴を統合しない場合
git merge origin/main

# コンフリクトが発生した場合、解決して続行

git push --force-with-lease

# プッシュが失敗した場合、再度git fetchから実行

```

### 作業用ブランチをクリーンアップするまで

```
git checkout main

# プルリクエストがマージされたら、mainを最新化しておく
git pull origin main

# ローカルブランチのクリーンアップ
git branch -d feature-branch

# リモートリポジトリのクリーンアップ（必要な時だけ）
git push origin --delete feature-branch

```
