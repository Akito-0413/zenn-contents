---
title: "フロントエンドカンファレンス福岡2026 参加レポート"
emoji: "📜"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["フロントエンド", "カンファレンス"]
published: true
---

# はじめに

9月12日に福岡県の九州産業大学 12号館にて開催された「Frontend Conference Fukuoka 2026」に参加してきました。
本記事では、参加するに至った経緯や聴講したセッションの中で印象的だったものをいくつかピックして感想を述べます。

@[card](https://frontend-conf.fukuoka.jp/2026/?hl=ja)

# 参加経緯

実務でフロントエンド側の開発を始めて、約1年半になろうとしています。

少人数で複数のアプリケーションの運用開発をしていることもあり、バグ改修や機能追加だけでなく、フレームワーク・ライブラリのメジャーアップデートや刷新、リファクタリングなど様々な経験を積んできました。

今後は、0からアプリを設計・構築するといった業務にもどんどん挑戦していきたい思いも強くありますが、フロントエンドに関する知識・知見がまだまだ足りていない実感もありました。

まずは、他の現場で働いているエンジニアの話も聞くことで自分に足りていない部分を認識し、今後の研鑽に繋げていければと思い、参加をしました。

# 印象に残ったセッションと感想

## Reactの設計論 / Architecturing a React Application

@[card](https://speakerdeck.com/uhyo/react-no-sekkeiron)

Reactが提供する宣言的UIや良いUXへの繋げ方、Async Reactの仕組みの解説が中心でした。

大切にしている思想や2つの保証・Laneモデルなどマクロな部分だけでなく、特定のコンポーネントやHookも交えたミクロな視点からの解説もされていて、実務へ落とし込むイメージがしやすく、とても参考になりました。
実務で利用している身として、「宣言的UIの恩恵を最大限受けているのか」の問いはかなり刺さりました（「受けられてないなこれ」って思いながら話を聞いていたんですが...）

トランジションを前提にして、Reactアプリを構築していくことが非常に重要であることが理解できました。

ステート更新中は、とりあえずローディングコンポーネント見せておいて...くらいでいつも開発していたんですが、要件・仕様に応じて、useTransisionやuseDeferredValueを適切に使い分けできるレベルに落とし込めたら良いレベルまで理解を深めたいです。

## Webプラットフォームで議論されているセキュリティ課題 / Security issues being discussed on Web Platforms

@[card](https://speakerdeck.com/petamoriken/security-issues-being-discussed-on-web-platforms)

WebプラットフォームやJavaScriptの仕様策定の現場で議論されているセキュリティ課題の紹介があり、DOM ClobberingやPrototype Pollution、Thenableの事例を扱って、脆弱性を解消していく中で出てくる課題・難しさを語るお話でした。

DOM ClobberingとPrototype Pollutionは、特にnpmパッケージでの脆弱性解消のタスクをやった時に知ったんですが、脆弱になり得る理由までは調べずにやっていたので、そこまで確認する習慣を付けたいと思いました。

仕様策定の際には既存の仕組みとの互換性を考慮しなければいけない難しさがあることを素人ながらも聞くことができたのは貴重な学びでした。
また、JavaScriptの仕様は特定のベンダーが決めているわけでなく、TC39という組織の中で議論をおこないながら進められていることを初めて知りました。

## AI Agent時代のリアーキテクチャ戦略と実践

@[card](https://speakerdeck.com/hokaccha/ai-agent-jidai-no-senryaku-to-jissen)

AIエージェントを使って開発をする際に意識すべきことや失敗しない仕組みや知見の共有が中心でした。

AIにどう書かせるかよりも、実装・検証・修正を繰り返せるループをどう設計するかが重要になるお話は、実務と重なる部分が多く、特に印象に残りました。

マイルストーンを検証可能な単位で区切っていくのは、AIのトークン節約にも繋がっていきそうだなとAI駆動開発を進める上でも有効な考え方だと感じました。
ときには、Human in the Loopも採用するなどして、どこに人間が入ればレバレッジが効いてくるかも考えるという視点は持っていなかったので、今後取り入れてみたい考え方でした。

## 安心して変更できるWebフロントエンドのつくり方

@[card](https://speakerdeck.com/pirosikick/anshin-shi-te-henkou-dekiru-web-furonto-endo-no-tsukurikata)

自動テストへの強い思いや何のテストを優先すべきか、現場に導入しようとした時の難しさを自身の考え・経験を中心に説明するお話でした。

話の半分は、Integration Testのことだったかなと思うくらいの熱量でした。
ドメイン理解が浅いまま開発タスクを進めるが故に良いテストが書けない話は、「締め切りを意識するとこうなるよなほんとに...」と、自分の経験とも重なりました。
テストコードが仕様書になるからこそ読まなきゃいけない、AIに書かせてCI落ちてないからヨシッ!!!はほんとにやめないとですね..

テスト容易性の説明はどっかの技術本で読んだかも...と思いつつも、自身が開発で意識できていないことを実感でき、自分の課題を改めて認識するきっかけになりました。

また、話をメモし続けている人が周りに多く、かなり有益に感じた参加者がたくさんいたんだろうなという印象です。
~~発表資料が公開されていなさそうなだけに、現地で聴講できた価値を強く感じました。
（ご本人のXアカウントには投稿されていませんでした）~~

カンファレンス後に発表資料をXにて発信されていたので共有しました。

# 他におこなわれていたセッション

当日聞くことができなかったお話もたくさんありました。
またどこかの機会でお聞きできたらという思いも残しつつ、発表資料が公開されているものは本記事にも掲載しておきます。

## Webの地図

@[card](https://speakerdeck.com/yosuke_furukawa/web-no-chizu)

## なぜテストを書くか？

@[card](https://bit.ly/fecf2026-lacolaco)

## AI時代のWebフレームワークはどこへ行く？

@[card](https://slides.yusu.ke/web-frameworks-in-the-ai-era)

## 日経電子版を支えていく Kasane Design System

@[card](https://speakerdeck.com/nikkei_engineer_recruiting/fec-fukuoka)

## Webで実用的な縦書きエディタは可能か？──現在地と普及に向けて

@[card](https://speakerdeck.com/karintou8710/web-de-jitsuyoutekina-tategaki-edita-ha-kanou-ka-genzaichi-to-fukyuu-ni-muke-te)

## 速さを追い求めたらHTMLになった - Studioレンダリングエンジン刷新の2年半 -

@[card](https://speakerdeck.com/ts020/hrc-frontend-conference-fukuoka-2026)

# 追記（2026/09/24）

今回のカンファレンス中の様子がYouTubeにて公開されていたので、追加しました。

## RoomA

@[card](https://youtu.be/HqmZmqVROzM)

## RoomB

@[card](https://youtu.be/r4JCSTBeze4)

## RoomC

@[card](https://youtu.be/Itn_tBeE41E)

# 最後に

このカンファレンスで自分に足りていないものはまだまだたくさんあったことが認識できました。
特に、もう1、2歩踏み込んで技術仕様や事象の背景を知っていく習慣をつけられるようになれればと感じた機会になりました。

余談ですが、イベントの参加レポートを書いていく中で、新しく入った知識と既に持っていた知見を脳内で整理することができたので、今後もこれを継続していきたいと思います。
