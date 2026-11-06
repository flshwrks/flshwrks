# flshwrks

自分や身近な人の困りごとを、Web アプリにして解いています。主に Next.js（App Router）と TypeScript で書き、生成 AI は Claude API と OpenAI API を使います。開発では Claude Code を相棒にしています。

## 実際に使われているもの

### シフト管理アプリ（非公開）

アルバイト先は、日本ではなじみの薄い地域の料理を扱う飲食店です。お客さんと言葉を交わし、まだ知られていない食文化の魅力を伝えることを何より大切にしています。ところが、シフトの希望を集め、組み、交代を調整する作業に、店で一番詳しい社員さんをはじめスタッフ全員の手間が取られていました。

この作業を軽くして、本来の仕事に時間を回してもらいたい。そう考えて、誰かに頼まれたわけではありませんが自分から提案し、提出から確定、交代までを Web で回すアプリを作りました。2026年から店舗で本番運用しています。

開発は AI（Claude Code）と組んで進め、設計・実装・運用を一人で担っています。運用でも AI を使っています。運用の台帳は自作の業務ポータルにまとめ、そこに実装した MCP サーバー経由で Claude が読み書きします。毎週の振り返りも Claude に定期実行させています。店舗の業務データを扱うため、コードは公開していません。

- Next.js + Supabase（Postgres）。複数店舗に対応し、権限は Postgres の行レベルセキュリティで店舗ごとに分けています
- 運用の仕組み: 暗号化したバックアップと復元コマンド、検証環境で確かめてから反映する手順、アプリ内の要望を GitHub の Issue に自動で起票する仕組みなど

## 生成 AI を使ったもの

| リポジトリ | 内容 | 技術 |
|---|---|---|
| [english-speaking-practice](https://github.com/flshwrks/english-speaking-practice) | AI とのリアルタイム会話でビジネス英語を練習するアプリ。会話後に Claude が添削し、学習者の弱点を記録して次回の指導に生かします | Next.js, OpenAI Realtime, Claude API（構造化出力）, Azure 発音評価, Neon Postgres |
| [case-lab](https://github.com/flshwrks/case-lab) | 戦略コンサルのケース面接を、AI の面接官と壁打ちして練習するアプリ | Next.js, Claude API |

## その他

| リポジトリ | 内容 | 技術 |
|---|---|---|
| [boki-quest](https://github.com/flshwrks/boki-quest) | 道具屋を経営しながら日商簿記3級を学ぶ Web ゲーム。[公開版はこちら](https://boki-quest-ebon.vercel.app)（ログイン不要） | Next.js, Vitest, Upstash Redis |
