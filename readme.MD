Scroll 이벤트를 이용한 예제를 공부합니다.

## scroll 관련 메소드
####  .scroll()
1. scroll 이벤트는 스크롤이 움직일 때 발생합니다. 이것은 window 객체에서 제공됩니다. [scroll01.html](http://choan616.dothome.co.kr/study/scroll/scroll01.html)
2. 스크롤이 가능한 프레임이나 overflow CSS 속성이 있는 요소의 scroll (또는 auto 속성) 에서도 발생합니다.[scroll02.html](http://choan616.dothome.co.kr/study/scroll/scroll02.html)

####  .scrollLeft()
1. scrollLeft(): 수평(가로) 스크롤의 위치는 픽셀 수치입니다. 스크롤바가 아주 왼쪽에 있거나 더이상 스크롤이 되지 않으며 그 수치는 0이 됩니다.[scroll03.html](http://choan616.dothome.co.kr/study/scroll/scroll03.html)
2. scrollLeft(가로스크롤값)- 조건에 일치하는 요소들의 수평 스크롤의 위치를 value값으로 세팅합니다.[scroll04.html](http://choan616.dothome.co.kr/study/scroll/scroll04.html)

#### .scrollTop()
1. 조건에 일치하는 요소들 중 첫번째 요소의 스크롤바의 수직 위치(y좌표)를 얻을 수 있습니다.[scroll05.html](http://choan616.dothome.co.kr/study/scroll/scroll05.html)
2. scrollTop( value )- 조건에 일치하는 요소들의 수직 스크롤의 위치를 value값으로 세팅합니다.[scroll06.html](http://choan616.dothome.co.kr/study/scroll/scroll06.html)

- - -

##세로 패럴락스 예제
예제는 배경 이미지인 별과 가운데에 있는 지구, 그리고 "parallax"라고 씌어진 이미지들로 구성되어 있습니다.

2. 스크롤 시 각각 다른 속도로 **세로 이동**을 하도록 코딩해봅시다.[scroll_01.html](http://choan616.dothome.co.kr/study/scroll/scroll_01/scroll_01.html)

##가로 패럴락스 예제
예제는 컨텐츠 영역, 뒤에 배경으로 먼 산, 가까운 산. 이렇게 세 부분으로 나뉘어 있습니다. 

1. 요소들을 **가로 이동**하도록 코딩해봅시다.[scroll_02.html](http://choan616.dothome.co.kr/study/scroll/scroll_02/scroll_02.html)
2. HTML5의 data 속성을 이용하여 애니메이션 되도록 코딩해봅시다.[scroll_03.html](http://choan616.dothome.co.kr/study/scroll/scroll_02/scroll_03.html)

##무한 스크롤 예제
페이지를 가장 아래로 스크롤 하면 내용이 계속 로딩이 되도록 무한 스크롤을 코딩해봅시다.

##이미지 변경 예제
스크롤에 따라 연속적인 이미지를 플립북 애니메이션처럼 재생이 되도록 코딩해봅시다.