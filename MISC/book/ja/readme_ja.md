---
description: Japanese Readme.
---

# yukicpl自述文件 -yukicpl Readme-

---

### 紹介
yukicplとは「初雪のコントロールパネル」である。  
簡単に言えば、元々自分用に作った、便利なスクリプトの集合みたいなもんです。
今の段階では　Debian >= 9 X86(AMD64)　および　Debian >= 9 ARM(ARM64)　プラットフォームをターゲットとしたものです。
クロスプラットフォームでの利用は何があっても保証しませんので、自己責任でお願いいたします。

元々はサーバー管理用に開発したものだが、これからはもっと日常的な機能にも考えてあります。  

**重要なお願い**
このパネルは元々自分用に開発したもので、かつ最初からほかの管理用パネルとの互換性など考えておりませんので。  
すべてのシステム上で、すべてのソフトウェアと共存できない可能性が想定できる。  
うまく実行できる、できなくとも、現存のすべてのエンバィアランメントやファイルシステムを破壊する恐れがある。  
念のため、まずは互換性検証からお試しください。できるだけほかのコントロールパネルとの合同使用は控えめにお願いいたします。
その他、元々マルチユーザー環境で検証していないため、ACLなどの権限管理は作ってありません。
かつ、このソフトウェアは複数のサードパーティーソフトウェアやオープンソースソフトウェアを管理し、利用している。
そのため、あらゆる操作の際にroot権限をリクエストする場合がある。
正式なサーバーでご利用の場合は、必ずシステム管理者の許可を得てください。
最後かつ一番重要なこと：リスクをご理解の上で、システム管理者の許可を得てからご使用ください。
このコントロールパネルにより、あらゆるセキュリティホールや損害などは、私に責任を問わないでください。

---

### クイックスタート
もしどう使うか迷うなら、[install.sh](https://github.com/hatsuyuki280/yukicpl/blob/master/MISC/install.sh)からご体験ください。  
またはこちらのコマンドを実行してください：
```
## 警告：このコマンドはユーザー、またはrootのパスワードを要求され、rootとして実行する。本実行前に install.sh の内容をよく確認してからご利用ください。
## 中身の日本語化はまだ終わっていない。
sudo su -c "bash <(wget -qO- https://yukicpl.yuki233.com/dist/etc/misc/install_jp.sh)"
```
上のコマンドを実行することで[yukicpl.sh](https://github.com/hatsuyuki280/yukicpl/blob/master/MISC/yukicpl.sh)をダウンロードされます。  
これから新しい機能を使う度に必要なパーツだけ自動でダウンロードできます。
どうしても一括で全部ダウンロードして欲しいなら、以下のコマンドを実行してください：
```
## 警告：このコマンドはユーザー、またはrootのパスワードを要求され、rootとして実行する。本実行前に install.sh の内容をよく確認してからご利用ください。
## 中身の日本語化はまだ終わっていない。
sudo su -c "bash <(wget -qO- https://yukicpl.yuki233.com/dist/etc/misc/install_full_jp.sh)"
```
インストールが終わったら、以下のように表示が出てくる：
```インストール完了しました。ターミナルで「yukicpl」を入力すれば実行できる。```

---

### 使用（未完成）
インストール終了後、yukicplは/usr/local/bin/ディレクトリの中に配置し、ほかのパーツは/usr/local/lib/yukicpl/ディレクトリの中にあります。
初期化時にインストールしたすべてのソフトウェアはパッケージマネージャー「APT」で管理しているので、それぞれ既定のディレクトリにインストールしている。
本コントロールパネルのディレクトリ使用は詳しくhttps://yukicpl.yuki233.com/dict_def_jp.json をご参照ください。

コントロールパネルを開始するには、rootユーザーで：
``` yukicpl ```
を実行してください。
一般ユーザーで実行した場合は、自動的にsudoコマンド（優先）かsuコマンドでrootまで権限をリクエストします。対応のパスワードをあらかじめ用意してください。  
コンフィグファイルが見つからない起動時に、自動的に初期化設定ウイザードが表示します。提示内容を従い、初期設定を終わらせてください。
手動でコンフィグファイルを編集する場合は、[yukicpl.conf](https://github.com/hatsuyuki280/yukicpl/blob/master/config-simple/yukicpl.conf)をご参照ください。
ドライモードで実行する場合は（すべてのコマンドは実行しない、コマンド内容はターミナルに表示しますので、そのまま確認できます。）以下のコマンドを任意のユーザーで実行してください。：
``` yukicpl --test ```

本コントロールパネルを正しく実行すると、機能選択ユーザーインターフェイスが表示します。
必要に応じて、選択し、ウイザードをしたがってお使いください。  
手動でインストールしたプログラムのコンフィグファイルを書く必要はありませんが、自分用にアレンジしたい場合はそれぞれ既定フォルダーをご参照ください。
---

#### ファスト機能（未完成）
まだ考案中です。完成後は更新するので、お楽しみください。  

---

### アンインストール（未完成）
セキュリティー向上のため、yukicplの「ワンキー退職」機能を削除しました。
（「ワンキー退職」では日本語の語源がないため、そのまま訳した。
実はrm -rfやdrop databaseなどのヤバいコマンドを使っているので、判断せず、すべて管理できるデータを削除し、実行したらすぐ退職届を書くならまだ間に合えるというミームです。）

正文に戻る、このコントロールパネルをリムーブするなら[uninstall.sh](https://github.com/hatsuyuki280/yukicpl/blob/master/MISC/uninstall.sh)を使ってください。  
またはこちらのコマンドを実行してください：
```
## 警告：このコマンドはユーザー、またはrootのパスワードを要求され、rootとして実行する。本実行前に uninstall.sh の内容をよく確認してからご利用ください。
## このスクリプトは文字列 yukicpl を含めたすべてのプロセスを中止するので、リスクを避けるために、プロセスを中止しますか？を聞かれたら、確実に表示したプロセスリストを確認してください。
sudo su -c "bash <(wget -qO- https://yukicpl.yuki233.com/dist/etc/misc/uninstall_jp.sh)"
```
実行したらウイザードをしたがって、アンインストールプロセスを完成させてください。  
**重要**
アンインストール時に「すべて削除」と選択すると、2回の確認後に確実に関連のあるすべてのファイルを削除されます。
このコントロールパネルから作ったすべてのエンバィアランメントやインストールしたプログラムで管理できるファイルはすべて含まれます。  
以下の文字が表示されたら、アンインストールは完了します。  
```アンインストールは完了しました。一部のファイルは使用中のため、削除できないかもしれません。手動でリブートして、リムーブしてください。```
アンインストールウイザードが終了直前には「アンケートに協力しますか？」と聞かれます。「N」を入力することで、アンケートを拒否できます。
（ただいま、アンケート機能は作り終わっていないため、アンケート聞くこともないし、何も送信しません。ご安心ください。）  
「N」以外の入力は、デフォルト同意とします。その後はwgetコマンドで、アンケートのカウンターに自動でアクセスし、送信します。
アンケート内容とシステムディストリビューション以外のユーザー情報は収集しないし、送信もしません。  
（送信する直前には送信内容と実行するコマンドを表示します）。  