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




