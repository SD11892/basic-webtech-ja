# shell: aggregate

## aggregation pipeline

aggregateを使うと複雑な処理が可能です。

```
> db.foods.aggregate([{$match: {visited: true}}, {$group: {_id: 'total', total: {$sum: '$counter'}}}])
```

他にも様々なoperatorがあります。例えば、次のようなものがあります。

- $sort,$skip,$limit 並び替えなど
- $unwind 配列の展開
- $sample ランダムピックアップ
- $lookup JOINみたいなもの
- $out コレクションへの書き込み

詳細は下記を参照。

- https://docs.mongodb.com/manual/aggregation/#aggregation-pipeline
- https://docs.mongodb.com/manual/reference/method/db.collection.aggregate/
- https://docs.mongodb.com/manual/reference/operator/aggregation-pipeline/

## 課題

1. 上記の動作を確認する
2. aggregation pipelineで$sortを使ってみる
3. aggregation pipelineで$sampleを使ってみる
4. ドキュメントをさらに登録して検索する
