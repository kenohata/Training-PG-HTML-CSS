2カラムレイアウト実装の実況
=========================
いよいよコピペではなく実践的に2カラムレイアウトを自分で書けるようになる練習をしましょう。このセクションにはサンプルソースが多く含まれていますが、それは制作の順序が分かるように「コマ撮り」しているものなので、一歩ずつ確認して進みましょう。

1. HTMLでマークアップ
---------------------------------------
まずは定石であるheader,content,footerそれと一番大きい外枠のoutlineを書いてしまいます。

::

	<html>
	<head>
	<title>2カラムレイアウト演習</title>
	<link rel="stylesheet" href="design.css" />
	</head>
	<body>
	<div id="outline">
	
	<!--header-->
	<div id="header">
	</div>
	<!--/header-->

	<!--content-->
	<div id="content">
	</div>
	<!--/content-->

	<!--footer-->
	<div id="footer">
	</div>
	<!--/footer-->
	
	</div>
	</body>
	</html>

この様に、body内にoutlineを置き、その中にheader,content,footerを配置しました。outlineとはページ全体の幅を固定するための枠だと思っていてください。ここまでHTMLでコーディングしていますが、同時に以下のような視覚的なイメージも持っていてください。

:: image:
	image.png

2. 2カラムに分割する。
------------------------------------------
::

	<html>
	<head>
	<title>2カラムレイアウト演習</title>
	<link rel="stylesheet" href="design.css" />
	</head>
	<body>
	<div id="outline">
	
	<!--header-->
	<div id="header">
	</div>
	<!--/header-->

	<!--content-->
	<div id="content">
	
	<!--main-->
	<div id="main">
	</div>
	<!--/main-->

	<!--sidebar-->
	<div id="sidebar">
	</div>
	<!--/sidebar-->
	
	</div>
	<!--/content-->

	<!--footer-->
	<div id="footer">
	</div>
	<!--/footer-->
	
	</div>
	</body>
	</html>

少し混乱してきたかもしれません。ここまでの枠をイメージすると、以下の様になります。

:: image:
	image.png

最初は難しいかもしれませんが、この枠作りが終わるまでは、CSSは全く書かずにここまで一気にHTMLを書いてください。ここは我慢です。

3. CSSでレイアウト
------------------------------------------


