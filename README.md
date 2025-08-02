# al-folio Minimal Sample for GitHub Pages

このリポジトリは al-folio をベースにした最小構成の学術ポートフォリオサイトのテンプレートです。
ローカルで重い環境を用意せず、GitHub Actions を使ってビルド・デプロイします。

## 含まれるファイル構成
- `Gemfile`: Jekyll と jekyll-scholar を指定（GitHub Pages のデフォルトビルドでは jekyll-scholar が使えないため、Actions でビルドします）。
- `_config.yml`: サイトの基本設定（タイトル、著者、論文設定など）。
- `index.md`: トップページの最小コンテンツ（自己紹介＋選択論文）。
- `_pages/publications.md`: 論文一覧ページ。bib ファイルを基に jekyll-scholar で生成される。
- `_bibliography/papers.bib`: サンプル論文（Einstein らの論文）。ここを自分の論文に書き換える。  
- `.github/workflows/deploy.yml`: GitHub Actions ワークフロー。`bundle exec jekyll build` でビルドし、`peaceiris/actions-gh-pages` で公開。

## 使い方（初期コミット手順）

1. このテンプレートをフォークまたはコピーして、リポジトリ名を `username.github.io`（ユーザーサイトとして使う場合）にするか、任意の名前でプロジェクトページにする。  
2. `_config.yml` の `title`, `author.name`, `author.affiliation`, `email`, `url` などを自分用に書き換える。  
3. `_bibliography/papers.bib` に自身の論文情報（BibTeX）を追加する。  
4. `index.md` 内の自己紹介文を編集する。  
5. `main` ブランチに push すると、自動的に GitHub Actions が走ってサイトがビルドされ、公開される。  
   - GitHub のリポジトリの Settings > Pages で `gh-pages` ブランチやデプロイ設定を確認する必要は基本的にありません。Actions が生成した静的ファイルが Pages に反映される。  
6. 数分待って `https://<your-username>.github.io/` で確認。

## カスタマイズのヒント
- 論文のスタイルは `_config.yml` の `scholar.style` を変更（例: `apa`, `ieee` など）。  
- 論文の言語設定は `scholar.locale` で調整可能（`en`, `ja` など）。  
- al-folio のレイアウトをさらに変更したければ、フォーク元の `/_layouts`, `/_includes`, `/_sass` を参照して CSS を上書きする。  
- プロフィールやプロジェクトは al-folio の標準構造に従って `_data` などに追加可能。

## トラブルシュート
- Actions のログで `bundle exec jekyll build` が失敗したら、Ruby のバージョンや gem の依存を確認。 `ruby/setup-ruby@v1` で指定しているバージョンを変えて試すことも有効です。  
- 論文が表示されない場合、BibTeX のエントリに構文エラーがないかをチェック。エントリ間の空行やカンマも正確に。  
- ビルド後にページが更新されない場合、Actions の最終ステップの `peaceiris/actions-gh-pages@v4` が成功しているか確認。  

## 例: 論文エントリの追加例
```bibtex
@inproceedings{sample2024,
  title={A Sample Conference Paper},
  author={Your, Name and Collaborator, B.},
  booktitle={Proceedings of the Example Conference},
  year={2024},
}
```

## 免責と拡張
このテンプレートは最小構成であり、必要に応じて al-folio のオリジナル機能（ブログ、更新履歴、プロジェクトセクションなど）を追加できます。

---
Generated on 2025-08-02
