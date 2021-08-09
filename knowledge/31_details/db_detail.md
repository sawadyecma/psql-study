# インメモリデータベース

- ゲームリーダーボード、セッションストア、リアルタイム分析などの、マイクロ秒の応答時間が必要でいつでもトラフィックが急増する可能性があるアプリケーションに最適。 
- キャッシュとかに有効
    - セッションストアはredis使った方がいい
- Postgresはインメモリデータベースではない
- インメモリは揮発性なので、永続化されない
    - ディスクの方がメンテナンス容易で価格も安い
- データはバックアップしておけばあとでみれる
    - 運用は面倒

# 行指向、列指向
- MySQLとPostgreSQLは行指向
- 列指向は属性ごとにデータが保存されている
- 時系列データに有効

# 行指向

- 空間的局所性が改善される
    - メモリ参照の局所性の一つ。
    - ある狭い範囲に存在する資源が集中的に参照される可能性の高さのこと
- 単一のブロックにはすべての列のデータが含まれる
- 特定の属性のみ取り出すクエリではコストが高くなる

# 列指向
- 集計処理を行う分析的なワークロードに適する
    - 農業のIoT領域とかで使えそう
- なんかマッピングする必要があるらしい。
- 使える可能性が出来たときに検討すればいいや。
    - わりとマイナー

# ワイドカラムストア
- 列指向とは別
- キーバリューのバリュー部分がさらにキーになる形式
- 結局はRDBと似た構造をとる


# データファイル

## インデックス構成表

## ヒープ構成表
- 書き込み順に保存される

## ハッシュ構成表
- 検索速度改善のためにソートされることもある

# インデックスファイル
- データエントリを保持する
- これはレコードを一意に識別、レコード検索する情報を含む。

- インデックスファイルとインデックス構成表はアプローチが違う

