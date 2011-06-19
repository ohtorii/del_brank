============================================================================
カーソル周りの空白を削除する秀丸マクロ
============================================================================

空白を削除するマクロは色々と公開されていますが、本マクロは下記特長があります。
    ・複数行選択へ対応。
    ・矩形選択へ対応。
    ・連続した空行の削除。



【動作】
・選択無し
    （変換前：|はカーソル位置）
        foo | bar
    （変換後）
        foobar

・複数行選択あり
    （変換前：<>は選択範囲）
        invoke <foo  bar
        hoge spam>   fire

    （変換後）
        invoke foobar
        hogespam   fire

・矩形選択（その１）
    （変換前：|は矩形選択の範囲、縦一直線に選択している。）
        foo=  |  0;
        bar=  | 1;
        hoge= |2;
    （変換後）
        foo=0;
        bar=1;
        hoge=2;

・矩形選択（その２）
    （変換前：<>は矩形選択の範囲）
        foo  =<  x  +  0  >;   //comment a
        bar  =<  x +  1   >;   //comment b
        hoge =< x + 2     >;   //comment c
    （変換後）
        foo  =x+0;   //comment a
        bar  =x+1;   //comment b
        hoge =x+2;   //comment c

・連続した空行の削除
    （変換前：|はカーソル位置）
        #include "foo.h"
        
        |
        
        #include "bar.h"
    （変換後）
        #include "foo.h"
        #include "bar.h"


【動作環境】
    秀丸エディタ ver8以降で動作します。


【連絡先】
    ohtorii
    http://d.hatena.ne.jp/ohtorii/
    https://github.com/ohtorii
