# 環境準備
以下のものを事前に準備しておく

- PC
- ターミナルソフト
- SSHの鍵
- GitHubのアカウント
- Skype for Business
- Google Cloud Platformのアカウント(なくてもわたしの環境を提供可能)

## ターミナルソフト(サーバへssh接続するために必要)
### windows(http://qiita.com/murachi1208/items/d6e4ce7ba75f1625fe51)
- Teraterm
- Poderosa
- putty
- Rlogin

### linux(https://wiki.archlinux.org/index.php/Category:Terminal_emulators)
- Xterm
- ディストリビューション付属のTerminal

### mac(https://rcmdnk.com/blog/2017/02/14/computer-mac/)
- iTerm
- OS付属のTerminal

## SSHの鍵作成(サーバにログインするために必要)
鍵のタイプはRSA、鍵の強度は2048が良いかと思います。

- [作成方法](https://git-scm.com/book/ja/v1/Git-%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC-SSH-%E5%85%AC%E9%96%8B%E9%8D%B5%E3%81%AE%E4%BD%9C%E6%88%90) 

- 上記のコマンドに鍵のタイプと強度をつけるとこんな感じ

```
ssh-keygen -t rsa -b 2048
```

- windowsは特に、各ターミナルソフトで作成できたりします。

## GitHub(ソースコードやドキュメント管理に必要)

- アカウントの作成(http://qiita.com/kooohei/items/361da3c9dbb6e0c7946b)
