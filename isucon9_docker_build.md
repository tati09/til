# ��
+ �ڍs��
    + OS�FRHEL 7.6
    + DB�FOracle EE  12.1.0.2
+ �ڍs��
    + OS�FRHEL 7.6
    + DB:Oracle SE2 12.1.0.2

# ��
�ڍs��(EE)����tablespace���[�h��expdp��DUMP�t�@�C���𐶐����A�ȉ��R�}���h�ňڍs��(SE2)��impdp�����{�����B
��DUMP�t�@�C���̈ړ��E�z�u�̎菇�͊���

```
[expdp from EE]
expdp hoge/hoge2@SourceSB tablespaces=SourceTableSpace directory=DATA_DUMP_DIR dumpfile=hogehoge.dmp logfile=ExportEE.log

[impdp to SE2]
impdp hoge/hogehoge2@TargetDB TABLESPACES=TargetTableSpace DIRECTORY=DATA_PUMP_DIR DUMPFILE=hogehoge.dmp LOGFILE=ImportSE2.log TABLE_EXISTS_ACTION=replace
��SourceTableSpace��TargetTablespace�̖��O�͓���
```

��L��impdp�����{����ƁApartition�@�\���L���� table�Eindex ���C���|�[�g�s�B

```
ORA-39083: �I�u�W�F�N�g�^TABLE:"owner"."tablename"�̍쐬�����̃G���[�Ŏ��s���܂���:
ORA-00439: �@�\�͗L���ł͂���܂���: Partitioning
```

# �Ώ�
impdp�̃I�v�V������ `PARTITION_OPTIONS=MERGE` ��ǉ�����B

```
impdp hoge/hogehoge2@TargetDB PARTITION_OPTIONS=MERGE TABLESPACES=TargetTableSpace DIRECTORY=DATA_PUMP_DIR DUMPFILE=hogehoge.dmp LOGFILE=ImportSE2.log TABLE_EXISTS_ACTION=replace
```

�Ȃ��A��L impdp �ł� index �C���|�[�g���ɃG���[�o�͂���邪�A�C���|�[�g�����͎��{����Ă���͗l�B
