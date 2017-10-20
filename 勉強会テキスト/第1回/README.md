# 

## ansibleサーバへのログイン
## Linuxサーバへのログイン
## 作業用ディレクトリの作成
## 簡単なgitの操作
## 簡単なansibleの操作
- [Getting Started](http://docs.ansible.com/ansible/latest/intro_getting_started.html)
- ansibleコマンド
    - hostsファイル作成

    - 実行

    ```
    ansible all -m ping -u ユーザ名
    ansible all -m shell -a "hostname" -u ユーザ名
    ansible all -m shell -a "cat /etc/shadow" -u ユーザ名
    ansible all -m shell -a "cat /etc/shadow" -u ユーザ名 -S
    ```
- ansible-playbookコマンド

## パッケージインストール
### Linuxサーバにログインをしてパッケージインストール

```
yum install wget
```

### ansibleサーバからansibleを使用してパッケージインストール
- [ansibleドキュメント](http://docs.ansible.com/ansible/latest/yum_module.html)
- playbookの作成

```
cd workdir
git clone https://github.com/tshst/linux-study.git
vi package_install.yml
ansible
```

ソースファイルのダウンロード
#Apache
wget http://ftp.tsukuba.wide.ad.jp/software/apache//httpd/httpd-2.4.27.tar.gz



ソースファイルからのインストール

RPM作成の環境準備(http://qiita.com/IK12_info/items/bcf695460363bae87eb9)
yum install rpmdevtools yum-utils
rpmdev-setuptree


RPM作成
•SRPMダウンロード
# ダウンロードサイトを探す
googleさんに聞いてもいいと思いますし、CentOS-vaultをリポジトリに登録しても良いかと思います。
以下は、私がやる、手動で探す方法です。
1. ディストリビューション(ここではCentOS)本家サイトからミラーサイトを探してアクセスする
https://www.centos.org/download/mirrors/
2. 日本のミラーサイトへアクセス(どこでもOK)
http://ftp.jaist.ac.jp/pub/Linux/CentOS/
3. [Parent Directory]をクリックして、1個上の階層にあがる
4. [CentOS-vault/]をクリック
5. [バージョン] - [os] - [Source] - [SPackages]と辿る(以下のURLの状態)
http://ftp.jaist.ac.jp/pub/Linux/CentOS-vault/7.3.1611/os/Source/SPackages/
6. 必要なパッケージのURLコピーして、wget

# SRPMをダウンロードする
## Apache(httpd-2.4.6-45.el7.centos.src.rpm)
wget http://ftp.jaist.ac.jp/pub/Linux/CentOS-vault/7.3.1611/os/Source/SPackages/httpd-2.4.6-45.el7.centos.src.rpm

RPMインストール
#インストール
rpm -ivh package_name --test
rpm -ivh package_name
# アップデート
rpm -Uvh package_name --test
rpm -Uvh package_name
# 削除
rpm -e package_name --test
rpm -e package_name

プライベートyumリポジトリ作成
•http://qiita.com/jz4o/items/33c3c7fc8a40145389d7


プライベートyumリポジトリに作成したパッケージを配布


プライベートyumリポジトリから作成したパッケージをyumでインストール
yum --enablerepo=local update
yum --enablerepo=local install package_name

