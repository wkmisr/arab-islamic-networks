# AINet-DB プロジェクトサイト：公開と更新の手順

## 1. 最初の公開（一度だけ）

1. GitHub で新しいリポジトリを作る（Public）。名前は `arab-islamic-networks` にします（`_config.yml` は設定済み）。
   - 別の名前にする場合は `_config.yml` の `baseurl` を `"/<リポジトリ名>"` に変えてください。
   - `<ユーザー名>.github.io` という名前にする場合は `baseurl: ""` にします。
2. `_config.yml` の `url` の `YOUR-GITHUB-USERNAME` を、自分のGitHubユーザー名に直す。
3. このフォルダの中身をリポジトリに push する（フォルダごとではなく、中身をルートに置く）。
4. リポジトリの Settings → Pages → Build and deployment で、Source を「Deploy from a branch」、Branch を `main` / `/ (root)` にして Save。
5. 1〜2分待つと `https://wkmisr.github.io/arab-islamic-networks/` に公開されます。

## 2. 研究会の記録（Events）を1件足す

`_posts/` に、次の名前でファイルを作ります。

    _posts/2026-11-20-hamburg-workshop.md

ファイル名は「開催日-英語のタイトル.md」です（この日付が表示日になり、新しい順に並びます）。中身の書き出し：

    ---
    title: "Workshop at the University of Hamburg"
    kind: "Workshop"
    place: "University of Hamburg"
    status: "Upcoming"
    summary: "トップページと一覧に出る1〜2文の要約。"
    ---
    本文（Markdown）。プログラム、登壇者、報告など。

- `kind` は Workshop / Seminar / Symposium など。`place` は開催地。
- `status: "Upcoming"` は開催前の目印です。開催後はこの行を消してください（自動では消えません）。
- 未来の日付でも表示されます。日付が未定なら、`date_label: "November 2026"` のように書くと、その表記が日付の代わりに表示されます（並び順にはファイル名の日付が使われます）。
- commit して push すれば自動で公開されます。

## 2b. ブログ記事を書く（Research ページの Blog 欄）

`_notes/` に Markdown ファイルを作ります（見本は `_notes/README.txt`）。

    _notes/2026-11-05-linking-to-wikidata.md

冒頭に `title`、`date`、`author`、`topic`、`summary` を書き、その下に本文を書いて push します。投稿すると、Research ページの Blog 欄と、トップページの「Research updates」に自動で出ます。

## 2c. 発表・刊行物を足す（Research ページの Presentations / Publications 欄）

`_outputs/` に、1件1ファイルで作ります（見本は `_outputs/README.txt`）。

    _outputs/2026-11-14-shinoda-jcas-symposium.md

`type: presentation`（ポスター・口頭・講演）か `type: publication`（論文・データセット）を指定します。予定のものには `status: "Upcoming"` を付け、終わったら消してください。スライドや論文のURLがあれば `link:` に入れると、題名からリンクされます。トップページの「Research updates」には、Blog と合わせて日付の新しい3件が出ます。

## 3. トップページの数字を更新する

`_data/stats.yml` の `value`（数字）と `as_of`（日付）を書き換えます。

## 4. あとで埋める場所

- リポジトリ公開後：`_config.yml` の `links.repository` に URL を入れると、Data ページとフッターにリンクが出ます。
- ブラウザ（検索ビューア）を公開する場合：`links.browser` に URL を入れます。
- ライセンス：`data.md` の最後の「Reuse」を、決まった文言に置き換えてください。

## 5. 公開前にご確認いただきたい点

- Events は研究会の議事録（4月3日、5月2日、5月14日、9月26日）から起こしました。予算・アルバイトの人選と待遇・個別の作業分担は載せていません。公開してよい粒度か確認してください。
- 5月の第3回は、フォルダ名が 05-15 ですが、議事録の開催日（5月14日）に合わせました。
- ハンブルク訪問（11月21〜22日）は、先方の名称・研究者名を出さない書き方にしています。許可が取れたら書き足してください。
- Team ページの共同研究者（Romanov氏、Van Steenbergen氏）は非表示です。許可が取れたら `_data/team.yml` の `show_collaborators` を `true` にすると表示されます。
- `project.md`・`team.md`・`data.md` の文面は、添付の科研費計画書から起こしました。チームの氏名の英語表記（特に篠田・土山）と、共同研究者2名の掲載可否、フッターの助成番号表記（JSPS KAKENHI Grant Number JP26K00196）を確認してください。
- 「AINet-DB」は仮称のため、About に "working title" と書いてあります。正式名称が決まったら `_config.yml` の `title` などを直します。
