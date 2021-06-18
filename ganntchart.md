## 日付を入れる
まずは日付と曜日を入れます。
コードの先頭でこちらのように書いておけば、
あとはタスクを追加する度に自動で更新して
くれます。

Project starts the 2020/5/11

## 休みの日を入れる
週末の土日や特定の休日のように、
仕事をしない日も入れておきます。

saturday are closed
sunday are closed
2020/5/20 is closed
2020/6/16 to 2020/6/18 is closed

## タスクを入れる
タスク名と、それにかける日数をこの
ように定義します。

[要求分析(計画)] lasts 3 days
「要求分析」というタスクを3日間で行うという事になります。
[T3 (1週間)] lasts 1 week
[T4 (1週間と4日)] lasts 1 week and 4 days

### 色を指定したい場合
[要求分析(実績)] lasts 2 days and is colored in Fuchsia/FireBrick

## タスクの開始日を設定する
タスクの開始は、動詞startで指定します。
[プロトタイプを設計] starts 2020-07-01
[プロトタイプをテスト] starts 2020-07-16

## タスクの終了
タスクの終了は、動詞endで指定します。
[プロトタイプを設計] ends 2020-07-15
[プロトタイプをテスト] ends 2020-07-25

## AND接続詞を使った1行宣言
[プロトタイプを設計] starts 2020-07-01 and ends 2020-07-15
[プロトタイプをテスト] starts 2020-07-16 and lasts 10 days

## 前のタスクが完了時にタスクが開始する場合
ただタスクを入れるだけだと、その開始日はデフォルトでプロジェクト開始日になります。

タスクによって開始日を分けたい場合は、こちらのように既存のタスクを基準にした設定をします。

[外部設計(計画)] starts at [要求分析(計画)]'s end

~day after/beforeとすることで、タスク開始日を1日単位で調整する事が出来ます。
[コーディング(実績)] starts 1 day after [内部設計(実績)]'s end

## マイルストーンを設定する
[要求仕様が決定] happens at [要求分析(計画)]'s end
この場合、要求分析タスクを行う際のマイルストーンとして、要求仕様の決定を設定しています。

## タスクのグループ分けを設定する
上から順に書き並べたタスクを、ステップごとや担当者ごとにグループ分けする事もできます。

[内部設計が決定] happens at [内部設計(計画)]'s end
[結合テストケースが決定] happens at [内部設計(計画)]'s end
-- Step 2 --
[コーディング(計画)] lasts 7 days
[コーディング(実績)] lasts 7 days and is colored in Fuchsia/FireBrick
例えばこのコードようにすると、内部設計までをStep1として、次のタスクであるコーディングからはStep2というグループにするという事になります。


## 短い名前
asキーワードを使用して、タスクに短い名前を定義できます。
[プロトタイプを設計] as [D] lasts 15 days
[プロトタイプをテスト] as [T] lasts 10 days
[T] starts at [D]'s end

## タスクの進捗
[foo] lasts 21 days
[foo] is 40% completed
[bar] lasts 30 days and is 10% complete

## 簡単なタスク継承
->で表現
[プロトタイプを設計] -> [プロトタイプをビルド]

## 参照
https://plantuml.com/ja/gantt-diagram
