# ��肽������
isucon9�\�I��Docker�œ���������

# ���s�菇
https://qiita.com/suzuki_sh/items/6192647a6dd6d6c1b396

# ��
+ Windows10
    + Docker version 20.10.7, build f0df350
    + git version 2.32.0.windows.1

# ���{���̏󋵏����Ȃ���
�ȉ����Q�l�ɂ���Windows��Docker�̃C���X�g�[��
https://qiita.com/gahoh/items/7b21377b5c9e3ffddf4a

Git-Clone�����悤�Ƃ��ăG���[
```
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

git�̌��J���Ɣ閧���̐ݒ�����Ă��Ȃ��̂ŁA�ȉ����Q�l�ɂ��Ď��{
https://zenn.dev/keikuchen/articles/cffa31d69ecaae7e91d7
���URL���ŎQ�Ƃ��Ă���y�[�W
https://eh-career.com/engineerhub/entry/2017/01/31/110000

�΍��͈ȉ��̂悤�ɐ���
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


���łɂ��̍\�z�菇��github��git push origin master���悤�Ƃ����github�̃��O�C����ʂ��\������邽�߁A
ID,Pass����͂��邪�A�ȉ��̂悤�ɃG���[�����\�������

```
Logon failed, use ctrl+c to cancel basic credential prompt
```


�ȉ����Q�l�ɂ��āAgit��Update���������
https://qiita.com/keep-going/items/985f31391a1099c41205




�菇�ł́A�����摜�t�@�C���̃_�E�����[�h��wget���g�p���Ă��邪�A�����Windows�Ȃ̂ňȉ��R�}���h�Ŏ��{
invoke-webrequest -uri https://github.com/isucon/isucon9-qualify/releases/download/v2/bench1.zip -outfile C:\--------\isucon9-qualify\bench1.zip
invoke-webrequest -uri https://github.com/isucon/isucon9-qualify/releases/download/v2/initial.zip -outfile C:\--------\isucon9-qualify\intial.zip






windows��make���g�������̂Ŏ����Q�l�ɂ��ăC���X�g�[�������B�����make�����s�����B
https://qiita.com/tyty96/items/f501f44a8d44e3fd6987


make�������ȉ��ňُ�I�����Ă���
```
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
docker run -v /result:/opt/initial-data/result -v /pwcache:/opt/initial-data/pwcache isucon9-qualify/initial-data
install -m 0644 result/initial.sql ../webapp/sql/initial.sql
process_begin: CreateProcess(NULL, install -m 0644 result/initial.sql ../webapp/sql/initial.sql, ...) failed.
make (e=2): �w�肳�ꂽ�t�@�C����������܂���B
make: *** [install-sql] �G���[ 2
```







