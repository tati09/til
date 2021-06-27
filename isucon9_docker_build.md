# 環境
+ 移行元
    + OS：RHEL 7.6
    + DB：Oracle EE  12.1.0.2
+ 移行先
    + OS：RHEL 7.6
    + DB:Oracle SE2 12.1.0.2

# 状況
移行元(EE)からtablespaceモードのexpdpでDUMPファイルを生成し、以下コマンドで移行先(SE2)にimpdpを実施した。
※DUMPファイルの移動・配置の手順は割愛

```
[expdp from EE]
expdp hoge/hoge2@SourceSB tablespaces=SourceTableSpace directory=DATA_DUMP_DIR dumpfile=hogehoge.dmp logfile=ExportEE.log

[impdp to SE2]
impdp hoge/hogehoge2@TargetDB TABLESPACES=TargetTableSpace DIRECTORY=DATA_PUMP_DIR DUMPFILE=hogehoge.dmp LOGFILE=ImportSE2.log TABLE_EXISTS_ACTION=replace
※SourceTableSpaceとTargetTablespaceの名前は同じ
```

上記のimpdpを実施すると、partition機能が有効な table・index がインポート不可。

```
ORA-39083: オブジェクト型TABLE:"owner"."tablename"の作成が次のエラーで失敗しました:
ORA-00439: 機能は有効ではありません: Partitioning
```

# 対処
impdpのオプションに `PARTITION_OPTIONS=MERGE` を追加する。

```
impdp hoge/hogehoge2@TargetDB PARTITION_OPTIONS=MERGE TABLESPACES=TargetTableSpace DIRECTORY=DATA_PUMP_DIR DUMPFILE=hogehoge.dmp LOGFILE=ImportSE2.log TABLE_EXISTS_ACTION=replace
```

なお、上記 impdp でも index インポート時にエラー出力されるが、インポート処理は実施されている模様。
