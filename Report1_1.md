#レポート課題1-2

##課題内容
仮想スイッチを停止時に、コントローラで以下のメッセージを表示するようにソースコードを変更せよ。ただし、"0xabc"はスイッチのdatapath_idの例である。

```
Bye 0xabc
```

##課題解答
hello_trema.rbに、スイッチとの接続が終了した際に呼び出されるイベントハンドラ"switch_disconnected"を定義する(引数にスイッチのdatapath_idをとる)。
その中に、ログメッセージを出力するためのloggerを使い、
通常レベルの情報（info）として、"Bye #{datapath_id.to_hex}!"を出力する。

具体的には、与えられたソースコードに以下のようにイベントハンドラを追加した。

```
  def switch_disconnected(datapath_id)
    logger.info "Bye #{datapath_id.to_hex}!"
  end
```

###課題ファイルへのリンク
[@hello-trema-shuya-abe/lib/hello_trema.rb](https://github.com/handai-trema/hello-trema-shuya-abe/blob/master/lib/hello_trema.rb)

