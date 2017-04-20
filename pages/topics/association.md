---
layout: page
title: 「相関ルール」で医薬品の活性や副作用を探る
permalink:
---

  「相関ルール」（association rule）という言葉をご存じでしょうか。残念ながら、「知っている」と言う方は、そう多くはないと思います。でも、実は皆さんがスーパーやコンビニで買い物をしているとき、密かにこの手法によって調査されている可能性はあります。さて、「相関ルール」とななんでしょう？

## 相関ルール
  私はスーパーへ行くと、食料品をまとめ買いするのでないときは、まず、果物売り場に行きます。値段や季節などにもよりますが、ミカンやリンゴなど、ごくふつうの果物が、だいたいの目当てです。次に、自宅には浄水器が取り付けにくいので、水の売り場を回ります。それから、ジュース売り場を回って、レジへ向かうというパターンが最も多いと思います。時には、シャンプーや洗剤、紅茶を買うこともありますが、そうしばしばではありません。
  さて、レジへ行けば、前の若い男性は、缶ビールを半ダースに、菓子パンと枝豆等を買っているようです（別に覗いたわけではありませんが、つい見えてしまうことがあります）。又別の日には、私が同じような買い物をしていると、前は若い女性で、缶チューハイを少しと、ポテトチップスと週刊誌のようなものを買っているようでした。だいたい閉店間際の遅い時間帯（最近はスーパーも随分遅くまで開いている）なので、これから帰って、いっぱいやろうという人も少なくないのでしょう。
  ここでこの３人の買い物パターンを表にしてみると、表1のようになります。

表1  ある日の某スーパーでの取引

取引番号 |  客  |    買い物1     |     買い物2    | 買い物3
---------|------|----------------|----------------|---------
    1    |  私  |   ジュース     |     リンゴ     |   水
    2    | 男Ａ |    ビール      |    菓子パン    |  枝豆
    3    | 女Ａ |  缶チューハイ  | ポテトチップス | 週刊誌
    ︙   |  ︙  |       ︙       |       ︙       |   ︙
    n    | 女n  |   シャンプー   |     リンス     | 乾電池

  さて、スーパーには毎日たくさんの人がやってきます。時間帯によって、買っていく商品も様々でしょうから、ここでは比較的遅い時間帯を考えましょう。私のような買い物パターンを取る人は、自分でいうのも何ですが、それほど多くはないと思います。しかし、こんな時間帯だと、男Ａや女Ａの様な買い物パターンを取る人は、それほど少なくないでしょう。今、数多くの調査から、
  「ビールを買う人は菓子パンや枝豆を買う可能性が高い」
という結論が得られたとします。ビールを買う人が枝豆を買う可能性が高いことは直感的にわかりますが、菓子パンというのはちょっとピンと来ません。しかし、どうもそのような傾向があることが数字に表れていたので、調査官は支店長に、ビールの売り場とパンの売り場を近づけるように進言してみました。そうすると、ビールを買う人がパンを買う可能性が倍になったというのです。どうもこのスーパーの周囲にはワンルームマンションが多くて、一人暮らしの人が、明日の朝食にとパンを買っていくのですが、買い物の中心は「今日のビール」なので、ともすれば忘れがちになるのかもしれません。
  さて、「可能性が高い」だけでは定量的とは言えません。そこで、表1のようなデータを定量的に把握する必要が出てきます。調査官が1ヶ月ほどの取引を纏めたところ、表2のような結果が得られたとします（フィクションですので念のため）。

表2  見つけ出した相関ルール

ルール番号 | 支持度 | 確信度 |    商品1   |      商品2
-----------|--------|--------|------------|------------------
    1      |    12% |    65% |   ビール   |      枝豆
    2      |    11% |    60% |  缶酎ハイ  | ポテトチップス
    3      |     9% |    58% | シャンプー |     リンス
    4      |     8% |    55% |  缶酎ハイ  |     週刊誌
    5      |     7% |    50% |   ビール   |      パン

  ここで「確信度」と言うのは、例えば、ビールを買った人の50%はパンも買っていくと言うことを示しており、「支持度」というのは、全体の取引（トランザクション）の中で、この例を指示するものが７％あったと言うことを示しています。調査官は、支持度と確信度がある程度以上のルールを支店長に進言し、商品の配置や動線の参考にすることにより、売り上げを伸ばすことができます。このような手法を「相関ルール」と呼び、データマイニング（たくさんある、必ずしも整理されていない雑多なデータから、有益な情報を抽出する方法の総称）の重要な手法の一つとなっています。

## 相関ルールの医薬学への応用
  さて、ここまでの話だと、「確かに相関ルールはわかったが、医薬学とどう関係があるのか？」と思われるかもしれません。しかし、既に相関ルールの医薬学への応用は熟してきています。
  例えば、高知医大の岩本ら[1]は、腫瘍マーカーと血液生化学項目との相関ルールの解析を試み、例えば腫瘍マーカーの一つであるAFP(αフェトプロテイン；肝細胞癌の腫瘍マーカーで、低出生体重児に多い肝芽腫の発見等にもよく用いられます）とAST、ALTとの関係を見いだしています。また、猪口ら[2]は、相関ルールをグラフ探索に適用できるよう拡張した手法を用いて、芳香族ニトロ化合物の変異原性の解析に成功しています。さらに、小川ら[3]は、SNPと臨床情報の関連を、相関ルールを応用して抽出しています。
  ごく最近、厚生労働省と医薬品医療機器総合機構が共同で、国に報告される全国からの副作用情報を元に、データマイニング手法を用いて、効能が異なる二つの新薬の組み合わせによる副作用を発見する試みに着手しました。まだ詳細は明らかになっていないが、恐らく相関ルールに類似した手法が採用される予定になっていると考えられます。国に寄せられる膨大な情報の中から、特定の副作用に対し、「医薬品Ａ」と「医薬品Ｂ」が関わっている確率が高い（支持度や確信度が高い）ことがわかれば、この二つの医薬品の組み合わせに関し注意が必要だと言うことがわかります。
  相関ルールやその拡張版の医薬学への適用は、まだまだ考えられます。「この構造式とこの置換基があれば、こんな活性がある」「この微生物とこの微生物がいるところはこんな環境だ」「この医薬品とこの医薬品を服用していると、本来希な重篤な副作用が起きやすい」など、いろんな適用が考えられます。皆さんもこの分野に足を踏み入れてみませんか？

## 参考文献
1. 岩本光実、片岡浩巳、小倉克巳、杉浦哲朗、第２２回医療情報学連合大会 22th JCMI (Nov., 2002) / 医療情報学 22 (Suppl.), 2002 pp.246-247.
2. Inokuchi, Akihiro; Washio, Takashi; Okada, Takashi; and Motoda, Hiroshi: J. Comput. Aided Chem., Vol. 2, pp.87-92 (2001)
3. 小川健二、吉田尚志、清水康、藤島清太郎、相磯貞和、Proceedings of Data Engineering Workshop 2002(DEWS2002), C5-4 (2002).