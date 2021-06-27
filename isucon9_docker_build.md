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




