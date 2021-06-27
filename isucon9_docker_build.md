# やりたいこと
isucon9予選をDockerで動かしたい

# 実行手順
https://qiita.com/suzuki_sh/items/6192647a6dd6d6c1b396

# 環境
+ Windows10
    + Docker version 20.10.7, build f0df350
    + git version 2.32.0.windows.1

# 実施時の状況書きなぐり
以下を参考にしてWindowsにDockerのインストール
https://qiita.com/gahoh/items/7b21377b5c9e3ffddf4a

Git-Cloneをしようとしてエラー
```
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

gitの公開鍵と秘密鍵の設定をしていないので、以下を参考にして実施
https://zenn.dev/keikuchen/articles/cffa31d69ecaae7e91d7
上のURL内で参照しているページ
https://eh-career.com/engineerhub/entry/2017/01/31/110000

対策後は以下のように成功
```
PS C:\Users\----------> git clone github:isucon/isucon9-qualify.git
Cloning into 'isucon9-qualify'...
Enter passphrase for key '---':
remote: Enumerating objects: 11636, done.
remote: Counting objects: 100% (81/81), done.
remote: Compressing objects: 100% (81/81), done.
remote: Total 11636 (delta 56), reused 0 (delta 0), pack-reused 11555 eceiving objects: 100% (Receiving36), 20.63 MiB | 8.23 MiB/s
 objects: 100% (11636/11636), 21.00 MiB | 8.26 MiB/s, done.
Resolving deltas: 100% (7718/7718), done.
```


ついでにこの構築手順をgithubにgit push origin masterしようとするとgithubのログイン画面が表示されるため、
ID,Passを入力するが、以下のようにエラー文が表示される

```
Logon failed, use ctrl+c to cancel basic credential prompt
```


以下を参考にして、gitをUpdateしたら解決
https://qiita.com/keep-going/items/985f31391a1099c41205




手順では、初期画像ファイルのダウンロードでwgetを使用しているが、今回はWindowsなので以下コマンドで実施
invoke-webrequest -uri https://github.com/isucon/isucon9-qualify/releases/download/v2/bench1.zip -outfile C:\--------\isucon9-qualify\bench1.zip
invoke-webrequest -uri https://github.com/isucon/isucon9-qualify/releases/download/v2/initial.zip -outfile C:\--------\isucon9-qualify\intial.zip






windowsでmakeを使いたいので次を参考にしてインストールした。正常にmakeが実行される。
https://qiita.com/tyty96/items/f501f44a8d44e3fd6987


make処理が以下で異常終了している
```
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
docker run -v /result:/opt/initial-data/result -v /pwcache:/opt/initial-data/pwcache isucon9-qualify/initial-data
install -m 0644 result/initial.sql ../webapp/sql/initial.sql
process_begin: CreateProcess(NULL, install -m 0644 result/initial.sql ../webapp/sql/initial.sql, ...) failed.
make (e=2): 指定されたファイルが見つかりません。
make: *** [install-sql] エラー 2
```







