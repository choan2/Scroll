Scroll 이벤트를 이용한 예제를 공부합니다.

## scroll 관련 메소드
####  $.scroll() - "scroll" JavaScript 이벤트를 바인딩 하거나 요소에 발생시킵니다.
scroll 이벤트는 스크롤이 움직일 때 발생합니다. 이것은 window 객체에서 제공됩니다. 또한 스크롤이 가능한 프레임이나 overflow CSS 속성이 있는 요소의 scroll (또는 auto 속성) 에서도 발생합니다..
```
<div id="target" style="overflow: scroll; width: 200px; height: 100px;">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit,
  sed do eiusmod tempor incididunt ut labore et dolore magna
  aliqua. Ut enim ad minim veniam, quis nostrud exercitation
  ullamco laboris nisi ut aliquip ex ea commodo consequat.
  Duis aute irure dolor in reprehenderit in voluptate velit
  esse cillum dolore eu fugiat nulla pariatur. Excepteur
  sint occaecat cupidatat non proident, sunt in culpa qui
  officia deserunt mollit anim id est laborum.
</div>
<div id="other">
  Trigger the handler
</div>
<div id="log"></div>
```
```
$( "#target" ).scroll(function() {
  $( "#log" ).append( "<div>Handler for .scroll() called.</div>" );
});
```
####  $.scrollLeft()
1.scrollLeft(): 수평(가로) 스크롤의 위치는 픽셀 수치입니다. 스크롤바가 아주 왼쪽에 있거나 더이상 스크롤이 되지 않으며 그 수치는 0이 됩니다.
```
<!DOCTYPE html>
<html>
<head>
  <style>
    p { margin:10px;padding:5px;border:2px solid #666; }
    </style>
  <script src="http://code.jquery.com/jquery-latest.js"></script>
</head>
<body>
  <p>Hello</p><p></p>
<script>var p = $("p:first");
			$("p:last").text( "scrollLeft:" + p.scrollLeft() );

			</script>

</body>
</html>
```
2.scrollLeft(가로스크롤값)- 조건에 일치하는 요소들의 수평 스크롤의 위치를 value값으로 세팅합니다.
```
<!DOCTYPE html>
<html>
<head>
  <style>
  div.demo {
  background:#CCCCCC none repeat scroll 0 0;
  border:3px solid #666666;
  margin:5px;
  padding:5px;
  position:relative;
  width:200px;
  height:100px;
  overflow:auto;
  }
  p { margin:10px;padding:5px;border:2px solid #666;width:1000px;height:1000px; }
	</style>
  <script src="http://code.jquery.com/jquery-latest.js"></script>
</head>
<body>
  <div class="demo"><h1>lalala</h1><p>Hello</p></div>
<script>$("div.demo").scrollLeft(300);
</script>

</body>
</html>
```
#### $.scrollTop()
1.조건에 일치하는 요소들 중 첫번째 요소의 스크롤바의 수직 위치(y좌표)를 얻을 수 있습니다.
```
<!DOCTYPE html>
<html>
<head>
  <style>
  p { margin:10px;padding:5px;border:2px solid #666; }
  </style>
  <script src="http://code.jquery.com/jquery-latest.js"></script>
</head>
<body>
  <p>Hello</p><p></p>
<script>var p = $("p:first");
$("p:last").text( "scrollTop:" + p.scrollTop() );

</script>

</body>
</html>
```
2.scrollTop( value )- 조건에 일치하는 요소들의 수직 스크롤의 위치를 value값으로 세팅합니다.
```
<!DOCTYPE html>
<html>
<head>
  <style>
div.demo {
background:#CCCCCC none repeat scroll 0 0;
border:3px solid #666666;
margin:5px;
padding:5px;
position:relative;
width:200px;
height:100px;
overflow:auto;
}
  p { margin:10px;padding:5px;border:2px solid #666;width:1000px;height:1000px; }
  </style>
  <script src="http://code.jquery.com/jquery-latest.js"></script>
</head>
<body>
  <div class="demo"><h1>lalala</h1><p>Hello</p></div>
<script>$("div.demo").scrollTop(300);
</script>

</body>
</html>
```

- - -

##세로 패럴락스 예제
예제는 배경 이미지인 별과 가운데에 있는 지구, 그리고 "parallax"라고 씌어진 이미지들로 구성되어 있습니다. 이 요소들을 스크롤을 했을때 각각 다른 속도로 ==세로 이동==을 하도록 코딩해봅시다.

##가로 패럴락스 예제
예제는 컨텐츠 영역, 뒤에 배경으로 먼 산, 가까운 산. 이렇게 세 부분으로 나뉘어 있습니다. 이 요소는 스크롤을 이용하면 요소들을 ==가로 이동==하도록 코딩해봅시다.
##무한 스크롤 예제
##이미지 변경 예제