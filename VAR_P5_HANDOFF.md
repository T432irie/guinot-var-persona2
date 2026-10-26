# VAR_p5 引き継ぎ（2026-10-26）

別端末・別チャットで続けるときの現状。返答は日本語。コミットは頼まれたときだけ。画像の新規生成は、頼まれるまでしない。

作業場所はワークスペース直下の `index.html`。入れ子の VAR_p5 フォルダはない。リモートは https://github.com/T432irie/guinot-var-persona2 。この作業はブランチ `persona2-rebuild`。`main` は仮画像を入れる前の公開側なので、仮素材を `main` に載せない。

別端末では次で同じ状態にする。

```bash
git fetch origin
git checkout persona2-rebuild
```

プレビューはワークスペースで `python3 -m http.server 8877 --bind 127.0.0.1` を起動し、`http://127.0.0.1:8877/index.html` を開く。8877 が LISTEN しているのに中身が空で返ることがある。その PID を止めてから起動し直す。`127.0.0.1:8765` は別の古い VAR ページなので使わない。確認時はブラウザキャッシュを無効にし、クエリ付き URL を使う。

## いまページが参照している仮素材

ファイル名が `_ai` のものは公開前の仮置き。撮影素材が来たら差し替える。HTML の「AI生成の仮画像」コメントは残す。

| 場所 | ファイル | 内容 |
| --- | --- | --- |
| ヒーロー | `assets/var_p5/hero_treatment_ai.jpg`（1200×1600） | 施術を受けるお客様。webp の source は削除済み。alt「VARの施術を受けるお客様」。直上の差し替えコメントも残す |
| 悩み 01 `#owner` | `worry_refuse_ai.jpg` | 腕で×を作り、不満そうな表情のお客様 |
| 悩み 02 | `worry_noreturn2_ai.jpg` | 帰っていくお客様を見送り、考え込むオーナー |
| 悩み 03 | `worry_staff2_ai.jpg` | スタッフの施術を横で見守るオーナー |
| 解決セクションの動画 | `treatment_video_ai.mp4` と `treatment_video_poster_ai.jpg` | 音声なしの仮動画。キャプションは「※動画はイメージです」 |
| 特徴 01 | `feature_experience2_ai.jpg` | 冷たいタオルでクールダウンし、微笑むお客様 |
| 特徴 02 | `feature_simple_ai.jpg` | 手だけで施術するスタッフ。機械は映さない |
| 特徴 03 | `feature_repeat_ai.jpg` | 施術後に笑顔で話すお客様とスタッフ |
| 体感ステップ 02 | `images/var-offre-nologo.jpg` / `.webp` | `VAR-OFFRE-MKTG` の上部ロゴ・文字を切った版。元画像は残す |
| 体感ステップ 03 | `cooldown_towel2_ai.jpg` | 冷たいタオルで両頬。figure はステップ 01 と同じ書き方（`ph--photo` もインライン height も付けない）。3枚とも 4:3 |
| 研修 | `training_ai.jpg` | `ph--photo`。スタッフに手順を教える |

ステップ 01 は既存の `images/p2-step01.jpg`。特徴2の施術写真は既存の `images/var-treatment-02.jpg`。商品写真は `images/03-VAR_Inverse_DET`。ロゴも既存のまま。

## 参照していないが残している仮ファイル

消さない。次の作業で戻す可能性がある。

`worry_noreturn_ai.jpg`、`worry_similar_ai.jpg`、`worry_staff_ai.jpg`、`cooldown_towel_ai.jpg`、`feature_experience_ai.jpg`、`treatment_expression_ai.jpg`、`staff_reaction_ai.jpg`

`worry_*_ai.jpg`（2 が付かない3枚）は、白い壁・ガラス・シャンデリアの明るいサロンで、顔なしの版。01 は空いた受付と白紙の予約帳、02 は同じ形の白い機器の列、03 は後ろ姿で肩に手。和風（障子、提灯、木、黒制服）には戻さない。顔を白布で覆う構図は禁止。

## 空のまま、または非表示

- `#buzz` は `hidden`。SNS 3枠 `{導入サロンのSNS投稿例 1〜3}` は許可前の実投稿に見えるため、画像を作らない。
- `{確認待ち：初月無料・美容液プレゼントの適用条件}`、`{調査の対象・期間・年}` など `{…}` は埋めない。数字、料金、お客様の声を作らない。確認用ラベルが必要なら `{確認待ち：〇〇}` だけ。
- 導入サロンの声は、元ペルソナ2の写真と文章（PRISMIC様、SPA香炉様、And Eyes様）。仮写真に差し替えない。SPA香炉 / SPA香月の正式表記は未確認。

## 画のルール

ヒーロー、特徴、ステップ、研修、動画の人物は、既存キャンペーンと同じ明るい髪・色白の海外女性。参考は `images/p2-hero-react.jpg`、`images/p2-step01.jpg`、`images/var-treatment-02.jpg`、`images/VAR-OFFRE-MKTG.jpg`。キラキラ、光の線、肌の比較、ビフォーアフターは再現しない。

悩み3枚は、のちに表情のある人物へ差し替わっている。白いパリ風インスティチュートが基準。生成画像に GUINOT のロゴ、看板、「SLIMMING ANTI-CELLULITE」の文字を写さない。実在機器、ブランド名、画像内の読める文字も禁止。

悩みの吹き出し文言は変えない。

1. クーポンで来た新規のお客様が、2回目に来てくれない
2. 近隣も似た機器・メニューばかり。エステ慣れしたお客様に響かない
3. 自分が施術すると評判がいいのに、スタッフだと同じ反応が出ない
