=========================
CSS 実践編
=========================

前章でCSSのごく基本的な語彙をひと通り学びました。今回はそれらの知識を元にして、Webサイトのデザインのもはや定石ともいえるテクニックを紹介します。

2カラムレイアウト
=========================
2カラムレイアウトとは、ページ全体をメインバーとサイドバーの2つの列に分けるレイアウトの事です。多くのWebサイトが採用しているレイアウトです。3カラムレイアウトというのもあります。

レイアウトの区切り方
-----------------------------------------
まず、ページ全体を縦方向に3つに分けます。header,content,footerという名前が一般的ですので今回はこの慣例にしたがいます。

HTML
::

	<html>
	<head>
	<title>Test</title>
	<link rel="stylesheet" href="design.css">
	</head>
	<body>
	<div id="header"></div>
	<div id="content"></div>
	<div id="footer"></div>
	</body>
	</html>

現段階でこのようになります。header,content,footerという名前のdivタグにより3つに分離しました。

次に、main,sidebarというid名のdivタグをcontentの中に作ります。

HTML
::

	<html>
	<head>
	<title>Test</title>
	<link rel="stylesheet" href="design.css">
	</head>
	<body>
	<div id="header"></div>
	<div id="content">
		<div id="main"></div>
		<div id="side"></div>
	</div>
	<div id="footer"></div>
	</body>
	</html>

これで2カラムレイアウトの枠組みは完成しました。次にCSSファイルを編集します。

CSS (design.css)
::

	#header{
		width:960px;

		margin:0px;
		padding:0px;
	}
	#content{
		width:960px;

		margin:0px;
		padding:0px;
	}
	#main{
		width:640px;

		margin:0px;
		padding:0px;
	
		float:left;
	}
	#sidebar{
		width:320px;

		margin:0px;
		padding:0px;
	
		float:right;
	}
	#footer{
		width:960px;
	
		margin:0px;
		padding:0px;
	
		clear:both;
	}

mainボックス、sidebarボックスに左右の回り込みを指定して、最後にfooterボックスで回り込みを解除しています。上記のサンプルソースには各ボックス間の余白はとっていないので、必要に応じて適宜調整してください。

大事な事は、
*	ブロック要素(div)で枠を作る
*	CSSで回り込み(float)をかける
*	clear:both;で回り込みを解除する。

です。これを応用すれば、3カラムレイアウトも可能です。

ホバーリンク (擬似クラス)
=========================
リンクしている文字列や画像の上にマウスのポインタを乗せると、色が変わったり画像が切り替わったりする物があります。こういう物をホバーリンクと呼びます。

id名やclass名を用いてCSSから見た目を指定して来ましたが、あらかじめ用意されているクラス名があり、それを「擬似クラス」と呼びます。id名は#、class名は.で指定しましたが擬似クラスは:を用いて指定します。

CSS
::

	a:link{
		/*リンク文字の通常状態*/
	}

	a:hover{
		/*上にマウスが乗っかっているとき*/
	}

	a:active{
		/*選択されているとき*/
	}

	a:visited{
		/*訪問済みリンク*/
	}

文字色を切り替えたいならば、colorオプションを、背景画像を切り替えたいならば、background-imageオプションを使って実装しましょう。もちろんその他のオプションも利用出来ます。

グローバルナビゲーションバー
=========================
ブログ


奇数行・偶数行の背景色色付け
=========================
odd,evenという擬似クラスをがあります。これはtrタグに用います。表の奇数行・偶数行でことなる背景色を適用するときに便利です。

HTML
::

	<html>
	<head>
	<title>Test</title>
	<link rel="stylesheet" href="design.css">
	</head>
	<body>
	<table>
	<tr><td>1</td><td>2</td><td>3</td></tr>
	<tr><td>1</td><td>2</td><td>3</td></tr>
	<tr><td>1</td><td>2</td><td>3</td></tr>
	</table>
	</body>
	</html>

CSS
::

	tr:odd{
	background-color:rgb(0,0,220);
	}
	tr:even{
	background-color:rgb(0,220,0);
	}

	

=========================




