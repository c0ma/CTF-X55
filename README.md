# CTF-X55
Simple XSS challenge

Try it here: http://adaxesoet.avlidienbrunn.se/?img=https://i.imgur.com/b5Pb4BN.gif

Write-ups: https://swehack.org/viewtopic.php?f=37&t=4508

```
<?php
	$img = $_GET["img"];
	$img = preg_replace('/(?:\b(?:(?:type\b\W*?\b(?:text\b\W*?\b(?:j(?:ava)?|ecma|vb)|application\b\W*?\bx-(?:java|vb))script|c(?:opyparentfolder|reatetextrange)|get(?:special|parent)folder|iframe\b.{0,100}?\bsrc)\b|on(?:(?:mo(?:use(?:o(?:ver|ut)|down|move|up)|ve)|key(?:press|down|up)|c(?:hange|lick)|s(?:elec|ubmi)t|(?:un)?load|dragdrop|resize|focus|blur)\b\W*?=|abort\b)|(?:l(?:owsrc\b\W*?\b(?:(?:java|vb)script|shell|http)|ivescript)|(?:href|url)\b\W*?\b(?:(?:java|vb)script|shell)|background-image|mocha):|s(?:(?:tyle\b\W*=.*\bexpression\b\W*|ettimeout\b\W*?)\(|rc\b\W*?\b(?:(?:java|vb)script|shell|http):)|a(?:ctivexobject\b|lert\b\W*?\(|sfunction:))|<(?:(?:body\b.*?\b(?:backgroun|onloa)d|input\b.*?\btype\b\W*?\bimage)\b| ?(?:(?:script|meta)\b|iframe)|!\[cdata\[)|prompt|confirm|(?:\.(?:(?:execscrip|addimpor)t|(?:fromcharcod|cooki)e|innerhtml)|\@import)\b)/ ','',$img);
	
	print '<br><br><center><img src="' . $img .'">';

?>
```
