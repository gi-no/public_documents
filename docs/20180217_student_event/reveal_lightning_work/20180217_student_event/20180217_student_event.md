### コーディングスキルチェック<br/>から就活→実務へ
#### 2018/02/17(土)
#### ギノ株式会社 エンジニア 高村

----------

## Agenda
- 自己紹介
  * あんた誰？
- コーディングスキルチェックについて
  * どんなスキルを期待している?
  * 採用側の活用例(ギノの例)
- 実務に <span style="color: red">**特に役立つ部分** </span>は？
- 逆に、<span style="color: lime">**測れていない部分** </span>はどうしたら？

<!-- ~1minutes -->

----------

## <img src="reveal_lightning_work/20180217_student_event/xKb_JO9V_400x400.jpg" style="vertical-align: middle;"/> 自己紹介
* **本名**：高村宏幸
* **前職**：某大手メーカー系SIer(マネジメント主体)
* **現職**：ギノのエンジニア
* **Twitter** : takamura1227
* **GitHub, Qiita** : yukimura1227

---

### 略歴

* 2008年4月 某メーカー系SIerに就職
  <!-- .element: class="fragment" -->
  - スマフォ向けアニメ見放題サービスの開発リーダー  
  (会員数200万人くらい)
  <!-- .element: class="fragment" -->
  - 技術重要！！て感じの会社じゃなくなってきたので脱出 <!-- .element class="fragment" -->

* 2016年3月 ギノへ転職 <!-- .element class="fragment" -->
  - 新卒サービス向けのエンハンス
  <!-- .element class="fragment" -->
  - POH8 恋するハッカソン ~ 君色に染まるアイドル ~
  <!-- .element class="fragment" -->
  - もし次の常駐先が女子エンジニアばっかりだったら
  <!-- .element class="fragment" -->
  - ロジックサマナー ~ 閃光の召喚プログラマ ~
  <!-- .element class="fragment" -->
  - プログラミングで一攫千金
  <!-- .element class="fragment" -->

<!-- ~3minutes -->

----------

### <span style="font-size: 90%;">コーディングスキルチェックについて</span>

---

### 何を計測しようとしているか  
**(期待しているスキル)**
- 基本的な <span style="color: lime"> **データ構造** </span>を知ってる？使える？
* <span style="color: lime"> **再帰処理** </span>とか手慣れてるよね？
* <span style="color: lime"> **計算量** の概念</span>を知っている？効率を意識できる？
* <span style="color: lime"> 基礎的な **アルゴリズム** </span>を知ってる？使える？
* 現実的な時間で作れる？ ...etc

<!-- ~5minutes -->

----------

## 採用側の活用例

---

### ギノの場合 ~スカウトでの活用~
![](reveal_lightning_work/20180217_student_event/スカウトでの活用.svg)
<!-- .element: style="width: 100%" -->

---

### ギノの場合 ~面接での活用~
![](reveal_lightning_work/20180217_student_event/面接での活用.svg)
<!-- .element: style="width: 80%" -->

<!-- ~7minutes -->

---

### コードはとても重要な情報
![](reveal_lightning_work/20180217_student_event/PAK86_codeing20140517_TP_V.jpg)
<!-- .element: style="width: 80%" -->

----------

### 実務で特に(汎用的に)  
### 役立つ部分は？

---

### その前に、実務ってなに？(大枠)

![](reveal_lightning_work/20180217_student_event/実務のイメージ.svg)
<!-- .element: style="width: 90%" -->

<!-- ~8minutes -->

---

### 初級プログラマの役割(イメージ)

![](reveal_lightning_work/20180217_student_event/実務のイメージ_最初.svg) <!-- .element: style="width: 90%" -->

---

### で、スキルチェックで期待しているスキルで特に大事なのは

---

### 基本的なデータ構造の理解

* 多くの場合データが土台になる
* データ構造の選択ミスで読みづらいものができる
* データ構造のミスは修正し辛い
* データモデリング、DB設計の基礎にもなる

<!-- ~9minutes -->

---

#### 具体例（実際にあった例）
~~~java
/** タスク本体 */
class Task {
    boolean finish = false;
    public void execute() {
        System.out.println("なんか処理");
        this.finish = true;
    }
}
~~~

~~~java
/** 一番優先度の高いタスクを実行する人 */
class TaskManager {
    private List<Task> taskList = new ArrayList<>();
    public TaskManager(List<Task> tasks) { this.taskList = tasks; }
    // 一番優先度の高いタスクを実行する
    public void executeFirstTask() {
        for( Task task : taskList ) {
            if(task.finish) continue;
            task.execute();
            break;
        }
    }
}
~~~
<!-- .element: style="font-size: 60%" -->

<!-- ~10minutes -->

---

#### キュー使えば
~~~java
/** タスク本体 */
class Task {
    public void execute() {
        System.out.println("execute task" + this.hashCode());
    }
}
~~~

~~~java
/** 一番優先度の高いタスクを実行する人 */
class TaskManager {
    private Queue<Task> taskQueue = new ArrayDeque<>();// ☆変更
    public TaskManager(Queue<Task> tasks) {
        this.taskQueue = tasks;
    }
    // 一番優先度の高いタスクを実行する
    public void executeFirstTask() {
        if(!taskQueue.isEmpty()) taskQueue.poll().execute();// ☆変更
    }
}
~~~
<!-- .element: style="font-size: 60%" -->

<!-- ~ 12minutes -->

---

#### **こんなのが積み重なって知らぬ間に辛くなる...**
![](reveal_lightning_work/20180217_student_event/N825_hakisaretake-bururui_TP_V.jpg)<!-- .element: style="width: 70%" -->

----------

### 逆に、測れていない部分  
### はどうしたら？

---

### 実務ってなに？ 再掲

![](reveal_lightning_work/20180217_student_event/実務のイメージ_最初.svg) <!-- .element: style="width: 90%" -->

---

### このあたりも知りたい

![](reveal_lightning_work/20180217_student_event/実務のイメージ_測れない部分.svg) <!-- .element: style="width: 90%" -->

<!-- ~ 13minutes -->

---

#### **何か作品つくって公開しておくと良い**

* 何かしら動かしてみせられるようなもの
<!-- .element: style="font-size: 80%;"-->
* 例えば、自分がちょっと面倒に思うことを改善するようなもの
<!-- .element: style="font-size: 80%;"-->
* とりあえず、あまり難しく考えないでつくってみるとよい
<!-- .element: style="font-size: 80%;"-->
* 話すの苦手な人は、特にモノに語らせるとよい
<!-- .element: style="font-size: 80%;"-->

<!-- ~ 14minutes -->

---

### おまけ
* paizaにもポートフォリオ関連動画があるのでご活用ください
<!-- .element: style="font-size: 80%;"-->
  - [学習動画:ITエンジニアの就活準備編2: ポートフォリオ制作](https://paiza.jp/works/career/primer/career2)

* 公開方法に困っている方は、(RubyOnRailsむけですが..)  
Qiita記事にまとめておいたので、よろしければどうぞ
<!-- .element: style="font-size: 80%;"-->
  - [Qiita：初学者向け：CI連携やHerokuへの自動デプロイも含めたRails環境構築の手引書](https://qiita.com/yukimura1227/items/9860360e7b9afeb3210d)
<!-- ~ 15minutes -->

----------

## おしまい  
時間都合で恐縮ですが、質問は  
休憩時間や懇親会の時にお気軽にどうぞ
